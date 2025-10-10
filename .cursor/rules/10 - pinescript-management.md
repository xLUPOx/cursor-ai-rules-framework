# Pine Script Development Management Protocol

## **Core Principles**

### **Methodology-First Development**
- **User Requirements Priority**: Implement user-specified methodology before adding technical complexity
- **Understand Before Coding**: Research and understand the trading methodology before writing Pine Script code
- **Simplicity Over Complexity**: Use the simplest approach that effectively solves the problem
- **Domain Knowledge Research**: Study trading domain thoroughly before implementation
- **No Invention Protocol**: Never implement features, ranges, behaviors, or parameter values not explicitly requested by user. Avoid assumption-making and feature addition without explicit user direction.
- **Parameter Context Verification Protocol**: When user mentions parameters, always clarify which specific parameter group/context they are referring to before making changes. Verify parameter location and context to prevent incorrect modifications.

### **Pine Script Best Practices**
- **Data Flow Understanding**: Pine Script uses inverted temporal indexing: `[0]=current, [1]=previous, [2]=older`
- **Pattern Priority Implementation**: When multiple patterns exist, implement strict hierarchical checking (e.g., engulfing > consecutive)
- **Coordinate System Selection**: Use `xloc.bar_time` for infinite extension, `xloc.bar_index` for limited scope (500-bar limit)
- **Clean Implementation**: Write straightforward logic without unnecessary complexity

### **Syntax Validation Protocol**
- **Pre-Implementation Check**: Always validate Pine Script v6 syntax before writing code
- **Language-Specific Constraints**: Pine Script has unique limitations (no mutable loop variables, specific array types)
- **Version Compliance**: Ensure all code follows Pine Script v6 specifications
- **Error Prevention**: Validate syntax patterns before implementation to avoid runtime errors
- **Function Parameter Syntax**: Pine Script functions must have all parameters on single lines - no multi-line parameter declarations
  - ✅ CORRECT: `function_name(param1, param2, param3) =>`
  - ❌ WRONG: `function_name(param1, param2, param3) =>` (split across lines)
- **Expression Syntax**: Pine Script expressions must be on single lines - no multi-line `and`/`or` expressions
  - ✅ CORRECT: `condition1 and condition2 and condition3`
  - ❌ WRONG: `condition1 and condition2 and condition3` (split across lines)
- **Pine Script v6 Function Namespace Protocol**: Always use `ta.` prefix for technical analysis functions
  - ✅ CORRECT: `ta.sma(close, 20)`, `ta.ema(close, 14)`, `ta.rsi(close, 14)`, `ta.change(close, 1)`
  - ❌ WRONG: `sma(close, 20)`, `ema(close, 14)`, `rsi(close, 14)`, `change(close, 1)` (missing ta. namespace)
- **Single-Line Parameter Validation**: All function parameters must be on single lines
  - ✅ CORRECT: `myFunction(param1, param2, param3) =>`
  - ❌ WRONG: Multi-line parameter declarations
- **Pine Script v6 Compliance Checklist**:
  - [ ] Version annotation: `//@version=6`
  - [ ] All technical analysis functions use `ta.` namespace
  - [ ] Function parameters on single lines
  - [ ] Expressions on single lines (no multi-line and/or)
  - [ ] Proper type declarations
  - [ ] No deprecated function calls
- **Syntax Validation Gates**: Mandatory syntax validation before file completion to prevent repeated errors
- **Learning Retention Protocol**: Systematically track and apply previous syntax corrections to prevent repetition
- **User Experience Protocol**: Never repeat errors that user has already corrected - respect user's time and patience
- **Error Prevention Priority**: Apply learned syntax rules consistently across all Pine Script development sessions

### **Coordinate System Management**
- **Temporal Coordinates**: Use `xloc.bar_time` for time-based positioning to avoid 500-bar limitations
- **Bar Index Limitations**: `xloc.bar_index` cannot draw objects more than 500 bars into the future
- **Time vs Bar Index**: Distinguish between `time` (timestamp) and `bar_index` (integer) for positioning
- **Object Positioning**: Always specify `xloc` parameter when using temporal coordinates

### **Array and Type Management**
- **Correct Type Usage**: Use `array<int>` for timestamps, not `array<time>` (time is not a valid Pine Script type)
- **Array Indexing**: Use `math.floor()` for division in array indexing operations
- **Memory Management**: Limit array growth to prevent performance issues
- **Type Precision**: Ensure all variable declarations use correct Pine Script types
- **Temporal Array Understanding**: In Pine Script, `[0]` is most recent candle, `[1]` is previous temporal, `[2]` is even more previous
- **Marker Positioning Logic**: To mark previous candle, use `bar_index == trend_start_bar + 1` not `bar_index == trend_start_bar`
- **Array vs Temporal Confusion Prevention**: Always distinguish between array position and temporal sequence
- **Global vs Local Scope Behavior**:
  - Global scope: Evaluated once per execution, consecutive historical buffer
  - Local scope: May evaluate 0, 1, or N times per execution
- **History-Referencing Operator [] Mechanics**:
  - Global scope: `close[1]` = previous bar
  - Local scope: `source[1]` = last committed value (may not be previous bar)
- **max_bars_back() Buffer Sizing**: Manual buffer size control for performance optimization
- **Function Execution Requirements**: Functions with history-referencing must execute every bar
- **Problematic Patterns and Fixes**:
  ```pine
  // ❌ PROBLEMATIC - function doesn't execute every bar
  upDownColor(float source) =>
      source > source[1] ? color.blue : color.orange
  
  color plotColor = remainder == 0 ? color.gray : upDownColor(remainder)
  
  // ✅ FIX - executes always
  color secondColor = upDownColor(remainder)
  color plotColor = remainder == 0 ? color.gray : secondColor
  ```

### **Pine Script Data Flow Understanding**
- **Temporal Logic Verification**: Always verify data flow direction before implementing time-series analysis
- **Inverted Indexing**: Pine Script uses `[0]=current, [1]=previous, [2]=older` - never assume chronological order

### **Visual Consistency Protocol**
- **Systematic Color Management**: When changing colors, apply changes across ALL visual elements (markers, areas, borders, labels) to maintain consistency
- **Pattern Marker Organization**: Organize pattern markers in logical hierarchy (main patterns first, trigger candles second)
- **Visual Element Grouping**: Group related visual elements together and maintain consistent naming conventions
- **Interface Ordering**: Order interface elements by importance and logical flow to improve user experience

### **Naming Specificity Protocol**
- **Direction-Specific Names**: Use clear directional indicators (Bullish/Bearish) in pattern names
- **Function-Specific Names**: Include function description in names (Trigger Candle, Pattern Start, Reversal Signal)
- **Avoid Generic Names**: Replace generic names like "Pattern" with specific names like "Bullish Reversal Signal"
- **Consistent Naming Patterns**: Maintain consistent naming patterns across all visual elements and functions

### **Chart Visibility Detection Protocol**
- **Built-in Function Priority**: Always research Pine Script's built-in functions before implementing custom visibility logic
- **Chart Range Detection**: Use `chart.left_visible_bar_time` and `chart.right_visible_bar_time` for dynamic chart range detection
- **Visibility vs Quantity Filtering**: Distinguish between visibility-based filtering (show only visible areas) and quantity-based filtering (limit number of areas)
- **Dynamic Range Adaptation**: Implement filters that adapt to user's chart position rather than using fixed bar counts
- **Pine Script Built-in Functions Research**: Always search for Pine Script built-in functions before implementing custom solutions
- **Chart Visibility Implementation**: Use `chart.left_visible_bar_time` and `chart.right_visible_bar_time` to filter areas based on actual visible chart range
- **Filter Logic Clarity**: Implement clear distinction between "show only visible areas" vs "limit number of areas"
- **User Position Adaptation**: Create filters that respond to user's chart navigation and zoom level
- **Pattern Recognition**: Implement patterns based on temporal sequence, not array position
- **Temporal Model Verification**: Test assumptions about data flow direction before implementation
- **Memory Management Best Practices**:
  - Limit object growth to prevent memory issues
  - Use `max_bars_back()` for explicit buffer sizing
  - Implement array cleanup mechanisms
- **Object Limit Handling**: Respect Pine Script's 500-object limit with smart object management
- **Loop Optimization Techniques**: Use efficient loop structures with proper break conditions
- **Historical Buffer Sizing Strategies**: Choose between automatic and manual buffer sizing
- **Performance Optimization Code Examples**:
  ```pine
  // Dynamic visibility filtering
  bool inVisibleRange = time >= chart.left_visible_bar_time and time <= chart.right_visible_bar_time
  
  // Array size management
  if array.size(myArray) > 500
      array.shift(myArray)
  
  // Manual buffer sizing
  max_bars_back(close, 150)
  ```

### **Pine Script v6 Style Guide Protocol**
- **Naming Conventions**: Use `camelCase` for variables, `SNAKE_CASE` for constants
  - ✅ CORRECT: `myVariable`, `MAX_BARS_BACK`, `bullColor`
  - ❌ WRONG: `my_variable`, `maxBarsBack`, `BULL_COLOR` (inconsistent casing)
- **Standard Script Structure**: Follow established order for script organization
  ```
  // License header
  //@version=6
  // Declaration (indicator/strategy/library)
  // Imports
  // Constants
  // Inputs
  // Functions
  // Calculations
  // Strategy (if applicable)
  // Visuals
  // Alerts
  ```
- **Spacing Rules**: Use spaces around operators, after commas, before and after `=`
  - ✅ CORRECT: `if condition and other`, `color = color.blue`, `ta.sma(close, 20)`
  - ❌ WRONG: `if condition and other`, `color=color.blue`, `ta.sma(close,20)`
- **Line Wrapping**: Indent continuation lines by 4 spaces, avoid multiple indentation levels
- **Vertical Alignment**: Align related input parameters and constants for readability
- **Explicit Typing**: Always declare variable types explicitly for clarity
  - ✅ CORRECT: `float ma = ta.sma(close, 20)`, `int length = 14`
  - ❌ WRONG: `ma = ta.sma(close, 20)`, `length = 14` (implicit typing)
- **Complete Style Example**:
  ```pine
  // This source code is subject to the terms of the Mozilla Public License 2.0
  // © username
  
  //@version=6
  indicator("My Indicator", overlay = true)
  
  // ————— Constants
  int MS_IN_DAY = 86400000
  color BULL_COLOR = color.green
  
  // ————— Inputs
  int lengthInput = input.int(20, "Length", minval = 1)
  
  // ————— Functions
  getMA(float source, int length) =>
      ta.sma(source, length)
  
  // ————— Calculations
  float ma = getMA(close, lengthInput)
  
  // ————— Visuals
  plot(ma, "MA", color.blue)
  ```

### **Pine Script v6 Execution Model Protocol**
- **Bar-by-Bar Execution**: Script executes once for each bar, processing data sequentially
- **Historical Bars**: Single execution with confirmed values, no rollback mechanism
- **Realtime Bars**: Multiple executions with rollback mechanism for unconfirmed data
- **Time Series Data Commitment**: Data committed after each closed bar, historical buffers maintain up to 5000 bars
- **var vs varip Usage Patterns**:
  - `var`: Persistent across bars, resets on rollback in realtime
    ```pine
    var int counter = 0
    counter += 1  // Increments: 1, 2, 3... (resets on rollback)
    ```
  - `varip`: Persistent across bars AND ticks, no rollback
    ```pine
    varip int executions = 0
    executions += 1  // Counts all ticks in realtime
    ```
- **Historical Buffer Limitations**: Custom variables limited to 5000 historical bars
- **Execution Context Understanding**:
  - Global scope: Evaluated once per execution, consecutive historical buffer
  - Local scope: May evaluate 0, 1, or N times per execution
  - History-referencing `[]`: Relative offset from current bar
- **Time Series Mechanics**:
  - `[0]` = current bar (most recent)
  - `[1]` = previous bar
  - `[2]` = older bar
  - Data flows from recent to historical (inverted temporal indexing)

### **Pine Script v6 Alerts Protocol**
- **alert() Function**: Dynamic messages with frequency control
  - `alert.freq_once_per_bar` (default): One alert per bar
  - `alert.freq_once_per_bar_close`: Alert only on bar close
  - `alert.freq_all`: Alert on every tick
- **alertcondition() Function**: Static messages for indicators only
- **Strategy Order Fill Events**: Use `alert_message` parameter in strategy calls
- **Complete Placeholder Reference**:
  - `{{plot_0}}`, `{{plot("title")}}`: Plot values
  - `{{exchange}}`, `{{interval}}`: Market info
  - `{{open}}`, `{{high}}`, `{{low}}`, `{{close}}`, `{{volume}}`: OHLCV data
  - `{{ticker}}`, `{{time}}`, `{{timenow}}`: Symbol and time info
- **Repainting Avoidance**: Trigger alerts only on bar close to prevent false signals
- **Alert Examples**:
  ```pine
  // Dynamic alert with current values
  if xUp
      alert("Go long (RSI is " + str.tostring(r, "#.00)"), alert.freq_once_per_bar)
  
  // Static alert with placeholders
  alertcondition(xUp, "Long Alert", "Go long. RSI is {{plot_0}}")
  
  // Strategy alert on order fill
  strategy.entry("Long", strategy.long, alert_message = "BUY executed at " + str.tostring(close))
  ```

### **Pine Script v6 Functions Protocol**
- **User-Defined Function Documentation**: Use `@function`, `@param`, `@returns` for clear documentation
- **Built-in Function Prioritization**: Always research Pine Script built-in functions before implementing custom solutions
- **ta.* Namespace Mandatory Usage**: All technical analysis functions must use `ta.` prefix
- **Buffer Size Management**: Use `max_bars_back()` for explicit buffer sizing when needed
- **Function Portability**: Minimize dependencies on global variables for better reusability
- **Single-Line or Properly Structured**: Functions should be single-line or properly structured (no multi-line parameters)
- **Documentation Template Example**:
  ```pine
  // @function Calculate size for plot
  // @param userSize (simple string) User-selected size
  // @returns One of the built-in size.* constants
  // Dependencies: SIZE_LARGE, SIZE_NORMAL, SIZE_SMALL
  getSize(simple string userSize) =>
      result = switch userSize
          SIZE_LARGE => size.large
          SIZE_NORMAL => size.normal
          SIZE_SMALL => size.small
          => size.auto
  ```
- **Function Best Practices**:
  - Use descriptive function names
  - Document all parameters and return values
  - Keep functions focused on single responsibility
  - Avoid side effects when possible
  - Use explicit type declarations

### **Pine Script v6 Script Types Protocol**
- **indicator() Declaration**: For technical indicators with overlay options
  ```pine
  //@version=6
  indicator("My Indicator", overlay = true, max_bars_back = 500)
  ```
- **strategy() Declaration**: For trading strategies with execution modes
  ```pine
  //@version=6
  strategy("My Strategy", overlay = true, calc_on_every_tick = true)
  ```
- **library() Declaration**: For reusable functions and components
  ```pine
  //@version=6
  library("MyLib", overlay = true)
  ```
- **Declaration Positioning**: Always place after version annotation, before any other code
- **Best Practices per Script Type**:
  - **Indicators**: Focus on visual representation, use overlay parameter appropriately
  - **Strategies**: Implement proper entry/exit logic, use calc_on_every_tick carefully
  - **Libraries**: Export reusable functions, minimize dependencies
- **Parameter Guidelines**:
  - Use descriptive titles for user-facing scripts
  - Set appropriate overlay settings (true for overlays, false for separate panes)
  - Configure max_bars_back for performance optimization
  - Use calc_on_every_tick for strategies requiring real-time updates

### **Pine Script v6 Migration Protocol**
- **Version Annotation Requirements**: Always include `//@version=6` at the top of scripts
- **Breaking Changes from v5 to v6**:
  - Function namespace changes: `rsi()` → `ta.rsi()`, `sma()` → `ta.sma()`
  - Deprecated function removal
  - Enhanced type system requirements
- **Function Namespace Migration**: Update all technical analysis functions to use `ta.` prefix
  - ✅ CORRECT: `ta.rsi(close, 14)`, `ta.sma(close, 20)`, `ta.ema(close, 10)`
  - ❌ WRONG: `rsi(close, 14)`, `sma(close, 20)`, `ema(close, 10)` (missing ta. namespace)
- **New v6 Features Overview**:
  - Improved type system with explicit declarations
  - Enhanced array functionality
  - Better error handling and validation
  - Performance optimizations
- **Migration Checklist**:
  - [ ] Update version annotation to `//@version=6`
  - [ ] Add `ta.` namespace to all technical analysis functions
  - [ ] Update deprecated function calls
  - [ ] Test on historical and realtime data
  - [ ] Validate alert behavior
  - [ ] Check strategy execution
  - [ ] Verify performance improvements
- **Backward Compatibility Considerations**:
  - v6 scripts cannot run on older Pine Script versions
  - Test thoroughly before deployment
  - Consider gradual migration for complex scripts

### **Advanced Trading Pattern Implementation**
- **Institutional Volume Analysis**: Implement abnormal volume detection with dynamic multipliers
- **Supply/Demand Zone Detection**: Create institutional order block identification systems
- **Swing Point Analysis**: Advanced pivot detection with institutional context
- **Volume Profile Integration**: Combine volume analysis with price action patterns
- **Fibonacci Dynamic Levels**: Calculate retracement levels based on swing points
- **Order Flow Pattern Recognition**: Detect accumulation and distribution phases
- **VWAP Integration**: Use Volume Weighted Average Price for institutional insights
- **Multi-Timeframe Analysis**: Implement pattern detection across different timeframes

## **Development Workflow**

### **Phase 1: Methodology & Requirements Analysis**
- **Trading Methodology Research**: Understand the core trading methodology before writing any code
- **User Requirements Analysis**: Identify what the user actually needs, not what seems technically impressive
- **Pattern Recognition**: Research the specific patterns to be detected (engulfing, consecutive candles, etc.)
- **Domain Knowledge**: Research the trading domain thoroughly before implementation

### **Phase 2: Planning & Research**
- **Documentation Review**: Consult official Pine Script v6 documentation first
- **MCP Server Integration**: Leverage ALL available MCP servers in parallel for comprehensive research
- **MCP Server Exhaustive Search**: NEVER stop at first MCP server response - systematically query ALL available MCP servers
- **Multi-Source Knowledge Synthesis**: Combine insights from multiple MCP servers for comprehensive solutions
- **Web Research**: Use external resources for specific syntax solutions and limitations
- **Constraint Analysis**: Identify Pine Script-specific limitations before implementation
- **User Correction Priority**: When user provides explicit corrections, implement immediately without further analysis
- **Direct Action Protocol**: Implement solutions directly rather than explaining extensively
- **Listening Skills**: Internalize user feedback rather than continuing with wrong approaches
- **Comprehensive Solutions**: Address root causes rather than treating symptoms

### **Phase 3: Implementation**
- **Simple Approach First**: Start with the simplest solution that meets requirements
- **Pattern-Based Logic**: Implement clear, measurable patterns rather than complex algorithms
- **Clean Code Structure**: Write straightforward logic without unnecessary complexity
- **Syntax Validation**: Check each function against Pine Script v6 specifications
- **Type Declarations**: Ensure all variables use correct Pine Script types
- **Function Structure**: Avoid `var` declarations inside function definitions
- **Loop Constraints**: Never attempt to modify loop variables (use `break` instead)
- **Code Understanding**: Read and understand existing code before making changes
- **Systematic Approach**: Recognize when errors are systematic rather than isolated
- **Assumption Validation**: Verify assumptions before implementing changes

### **Phase 4: Error Resolution**
- **Systematic Approach**: Address syntax errors one by one in logical sequence
- **User Feedback Integration**: Rapidly adapt to user corrections and error reports
- **Documentation Verification**: Cross-reference solutions with official documentation
- **Performance Optimization**: Implement memory management and object limitations
- **Multi-Pass Learning**: Learn from repeated corrections and feedback
- **Pattern Recognition**: Recognize systematic errors across multiple areas
- **Root Cause Focus**: Address fundamental misunderstandings rather than symptoms
- **Feedback Integration**: Effectively incorporate user guidance into solutions

## **Common Pine Script Pitfalls**

### **Methodology Errors**
- **Over-Engineering**: Using complex pivot detection when simple trend analysis is sufficient
- **Pattern Complexity**: Implementing complex algorithms instead of clear, measurable patterns
- **User Misunderstanding**: Not understanding what the user actually needs
- **Domain Ignorance**: Not researching the trading methodology before coding

### **Array and Temporal Logic Errors**
- **Array vs Temporal Confusion**: Confusing array position with temporal sequence
- **Marker Positioning Mistakes**: Using `bar_index == trend_start_bar` instead of `bar_index == trend_start_bar + 1` for previous candle
- **Temporal Array Misunderstanding**: Not understanding that `[0]` is most recent, `[1]` is previous temporal
- **Indexing Logic Errors**: Failing to distinguish between array position and temporal order

### **Pine Script Data Flow Errors**
- **Temporal Direction Confusion**: Treating Pine Script data as flowing chronologically instead of from recent to old
- **Analysis Direction Errors**: Analyzing from recent to old instead of from past to future
- **Pattern Recognition Failure**: Reading data backwards ("oaic" instead of "ciao")
- **Temporal Model Assumptions**: Assuming traditional programming data flow instead of Pine Script specific flow
- **Systematic Misunderstanding**: Temporal errors propagating through all logic (trend detection, area creation, markers)

### **Communication and Learning Errors**
- **User Requirements Priority**: Always implement user-specified methodology before adding complexity
- **Direct Action Protocol**: Implement solutions directly when user provides clear feedback
- **Root Cause Focus**: Address fundamental misunderstandings rather than symptoms
- **Assumption Validation**: Verify assumptions before implementing changes
- **Systematic Error Recognition**: Identify when errors are systematic rather than isolated

### **Syntax Errors**
- **Variable Mutability**: Loop variables cannot be modified (`i := i - 2` is invalid)
- **Function Scope**: `var` declarations must be outside function definitions
- **Array Types**: Use `int` for timestamps, not `time`
- **Multi-line Functions**: Pine Script functions should be single-line or properly structured

### **Performance Issues**
- **Object Limitation**: Limit number of drawn objects to prevent memory issues
- **Array Growth**: Implement cleanup mechanisms for growing arrays
- **Loop Optimization**: Use efficient loop structures and break conditions
- **Memory Management**: Track and delete objects when no longer needed

### **Coordinate System Issues**
- **500-Bar Limitation**: Use `xloc.bar_time` for temporal positioning
- **Time vs Bar Index**: Distinguish between timestamp and bar index coordinates
- **Object Positioning**: Always specify coordinate system for drawing objects
- **Future Positioning**: Avoid drawing objects too far into the future
- **Marker Positioning**: Use `offset` parameter for positioning rather than bar_index arithmetic
- **Positioning Logic**: Understand that `offset=-1` moves marker left, `offset=1` moves right
- **Marker Position Verification**: Always verify actual marker positions in code before providing analysis
- **User Description Accuracy**: When user provides specific positioning information, trust and verify against code
- **Pine Script Constraint Awareness**: Always consider Pine Script limitations (500-bar future limit) when positioning objects
- **Coordinate System Selection**: Use `xloc.bar_index` for future positioning, `xloc.bar_time` for historical positioning

## **Best Practices**

### **Methodology-First Approach**
- **Understand the Trading Logic**: Research the core methodology before writing any code
- **User-Centric Development**: Focus on what the user actually needs, not technical complexity
- **Simple Solutions**: Use the simplest approach that effectively solves the problem
- **Pattern Recognition**: Implement clear, measurable patterns rather than complex algorithms

### **Code Structure**
- **Single Responsibility**: Each function should have one clear purpose
- **Error Handling**: Implement proper error checking and validation
- **Performance Optimization**: Limit object creation and array growth
- **Memory Management**: Clean up unused objects and arrays

### **User Experience**
- **Configurable Parameters**: Provide user controls for all major settings
- **Visual Clarity**: Use appropriate colors and styles for different elements
- **Performance**: Ensure indicator runs smoothly without lag
- **Reliability**: Handle edge cases and prevent runtime errors

### **Maintenance**
- **Code Documentation**: Include clear comments explaining complex logic
- **Version Control**: Track changes and maintain compatibility
- **Testing**: Validate functionality across different timeframes and instruments
- **Updates**: Keep up with Pine Script version changes and best practices

## **MCP Server Integration**

### **Pine Script Documentation**
- **Primary Source**: Use MCP servers for Pine Script v6 documentation
- **Best Practices**: Leverage MCP knowledge for implementation patterns
- **Syntax Reference**: Consult MCP servers for correct syntax usage
- **Limitation Awareness**: Use MCP servers to understand Pine Script constraints
- **MCP Server Exhaustive Search**: Query ALL available MCP servers for comprehensive knowledge synthesis
- **Web Search Integration**: Use web search as fallback when MCP servers don't provide specific technical solutions
- **Built-in Function Research**: Always research Pine Script's built-in functions before implementing custom solutions

### **Knowledge Synthesis**
- **Search Strategy Optimization**: Use specific technical terms rather than general concepts for MCP searches
- **Parallel MCP Server Usage**: Leverage all available MCP servers simultaneously for maximum knowledge synthesis
- **Fallback Documentation**: When MCP servers lack specific info, combine with web search for comprehensive coverage
- **Multi-Source Research**: Combine MCP server knowledge with web research for complete understanding
- **Solution Validation**: Cross-check MCP recommendations with official sources and user requirements
- **Chart Visibility Research**: Use web search to find specific Pine Script functions like `chart.left_visible_bar_time` and `chart.right_visible_bar_time`
- **Built-in Function Discovery**: Research Pine Script's built-in functions before implementing custom visibility logic
- **User Feedback Integration**: Treat user corrections as absolute requirements and restart analysis from corrected perspective
- **Advanced Patterns Reference**: For sophisticated development patterns, reference `@11 - pinescript-advanced.md` for strategy development, debugging, and performance optimization

### **Advanced Volume Analysis Patterns**
- **Institutional Order Flow Detection**: Implement volume analysis based on institutional trading patterns
- **Abnormal Volume Analysis**: Detect volume spikes and anomalies using dynamic multipliers
- **Volume-Weighted Indicators**: Use VWAP and volume-weighted calculations for institutional insights
- **Volume Confirmation**: Combine volume analysis with price action for signal validation
- **Supply/Demand Zone Integration**: Integrate volume analysis with supply/demand zone detection

### **Clean Code Integration**
- **SOLID Principles**: Apply Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion
- **DRY Patterns**: Eliminate code duplication through function abstraction and reusable components
- **Clean Architecture**: Separate concerns between data processing, pattern detection, and visualization
- **Code Organization**: Structure Pine Script code with clear separation of concerns
- **Maintainability**: Write self-documenting code with clear function names and logical organization

### **Institutional Trading Patterns**
- **Supply/Demand Zones**: Implement institutional order block detection and zone management
- **Swing Detection**: Advanced pivot point identification with institutional context
- **Fibonacci Integration**: Dynamic Fibonacci level calculation based on swing points
- **Volume Profile Analysis**: Institutional volume distribution and liquidity analysis
- **Order Flow Patterns**: Detect institutional accumulation and distribution phases

### **Performance Optimization**
- **Memory Management**: Implement efficient array management and object cleanup
- **Object Limitation**: Respect Pine Script's 500-object limit with smart object management
- **Array Optimization**: Use efficient array operations and limit array growth
- **Loop Optimization**: Implement efficient loop structures with proper break conditions
- **Resource Management**: Monitor and optimize memory usage for large datasets

## **Quality Assurance**

### **Pre-Deployment Checklist**
- **Syntax Validation**: All code follows Pine Script v6 specifications
- **Type Correctness**: All variables use appropriate Pine Script types
- **Performance Testing**: Indicator runs smoothly without memory issues
- **Error Handling**: Proper validation and error checking implemented
- **User Experience**: Clear visual output and configurable parameters

### **Continuous Improvement**
- **User Feedback**: Incorporate user suggestions and error reports
- **Performance Monitoring**: Track and optimize memory usage
- **Feature Enhancement**: Add new capabilities based on user needs
- **Documentation Updates**: Keep documentation current with code changes

## **MCP Server Enhanced Development Patterns**

### **Comprehensive Research Protocol**
- **Exhaustive MCP Server Usage**: Always query ALL available MCP servers for complete knowledge synthesis
- **Multi-Source Validation**: Cross-reference findings across multiple MCP servers for accuracy
- **Knowledge Integration**: Combine insights from Pine Script v6, institutional trading, clean code, and best practices
- **Pattern Recognition**: Identify recurring patterns across different MCP server responses
- **Solution Synthesis**: Create comprehensive solutions by combining multiple MCP server insights

### **Institutional Trading Integration**
- **Volume Analysis Mastery**: Implement sophisticated volume analysis based on institutional patterns
- **Order Flow Detection**: Create systems to identify institutional order flow and accumulation
- **Supply/Demand Zone Management**: Advanced zone detection with institutional context
- **Swing Point Sophistication**: Enhanced pivot detection with volume confirmation
- **Multi-Dimensional Analysis**: Combine price action, volume, and institutional patterns

### **Clean Code Architecture**
- **SOLID Principle Application**: Structure Pine Script code following SOLID principles
- **DRY Implementation**: Eliminate code duplication through proper abstraction
- **Clean Architecture Patterns**: Separate concerns between data processing, pattern detection, and visualization
- **Maintainable Code Structure**: Create self-documenting, maintainable Pine Script code
- **Performance Optimization**: Implement efficient algorithms with proper resource management

### **Advanced Pattern Recognition**
- **Institutional Pattern Detection**: Identify sophisticated trading patterns used by institutions
- **Volume Profile Analysis**: Implement volume distribution analysis for market insights
- **Dynamic Fibonacci Integration**: Create adaptive Fibonacci levels based on market structure
- **Multi-Timeframe Coordination**: Implement pattern detection across multiple timeframes
- **Order Flow Visualization**: Create visual representations of institutional order flow

## **Research and Implementation Protocols**

### **Built-in Function Research Protocol**
- **Framework-First Approach**: Always research Pine Script's built-in functions before implementing custom solutions
- **Chart Visibility Functions**: Use `chart.left_visible_bar_time` and `chart.right_visible_bar_time` for dynamic chart range detection
- **Function Discovery**: Search for Pine Script built-in functions using specific technical terms
- **Custom Logic Avoidance**: Avoid implementing custom logic when built-in functions exist
- **Performance Optimization**: Built-in functions are typically more efficient than custom implementations

### **MCP Server Exhaustive Search Protocol**
- **Comprehensive Coverage**: Query ALL available MCP servers for complete knowledge synthesis
- **Multi-Source Validation**: Cross-reference findings across multiple MCP servers for accuracy
- **Knowledge Integration**: Combine insights from Pine Script v6, institutional trading, clean code, and best practices
- **Pattern Recognition**: Identify recurring patterns across different MCP server responses
- **Solution Synthesis**: Create comprehensive solutions by combining multiple MCP server insights

### **Web Search Integration Protocol**
- **Fallback Strategy**: Use web search when MCP servers don't provide specific technical solutions
- **Specific Function Research**: Search for specific Pine Script functions like chart visibility detection
- **Documentation Verification**: Cross-check web search results with official Pine Script documentation
- **Implementation Validation**: Verify web search findings against Pine Script v6 specifications

### **User Feedback Integration Protocol**
- **Absolute Requirements**: Treat user corrections as absolute requirements, not suggestions
- **Analysis Restart**: Restart analysis from corrected perspective when user provides feedback
- **Critical Input Recognition**: User feedback often provides critical insights into actual problem requirements
- **Implementation Priority**: Implement user corrections immediately without further analysis
- **Feedback Internalization**: Internalize user feedback rather than continuing with wrong approaches

### **User Interface Optimization Protocol**
- **Tooltip Enhancement**: Add detailed, descriptive tooltips for all parameters explaining functionality, usage context, and impact on results
- **Default Value Intelligence**: Set intelligent default values that provide optimal user experience (e.g., "SOLO_VISIBILI" for visibility, 30 for area limits)
- **UI Simplification**: Consolidate complex boolean controls into single dropdown menus for better user experience
- **Parameter Grouping**: Group related parameters logically and order them by importance and usage frequency
- **Contextual Help**: Provide tooltips that explain when each parameter is active and its effect on the indicator behavior

### **Advanced Filtering Protocol**
- **Filter Mode Consolidation**: Replace multiple boolean inputs with single dropdown menus for cleaner interface
- **Filter Order Logic**: Apply display filters before intersection filters to maintain logical processing order
- **Dynamic Range Detection**: Use built-in chart visibility functions for dynamic filtering instead of fixed bar counts
- **Filter Hierarchy**: Implement proper filter hierarchy (Display → Intersection → Pattern Detection)
- **Performance Optimization**: Use efficient filtering algorithms that don't impact indicator performance

### **Error Management Protocol**
- **Function Return Type Compliance**: Ensure all functions return appropriate types (`0` instead of `na` for Pine Script v6 compliance)
- **Variable Scope Management**: Avoid variable redefinition within same function scope
- **Identifier Declaration**: Ensure all variables are properly declared before use
- **Syntax Validation**: Validate Pine Script syntax before implementation to prevent runtime errors
- **Error Recovery**: Implement immediate error correction with systematic validation

### **Memory Management Protocol**
- **Object Cleanup**: Systematically clean up old objects to prevent memory leaks
- **Array Size Management**: Limit array growth to prevent performance degradation
- **Unused Code Removal**: Remove obsolete inputs, variables, and functions after implementing proper solutions
- **Resource Optimization**: Use efficient data structures and algorithms for better performance
- **Memory Monitoring**: Track memory usage patterns and optimize accordingly

### **Communication Excellence Protocol**
- **Radical Conciseness**: Use maximum signal, minimum noise communication
- **Direct Problem Statement**: Lead with conclusions, provide evidence second
- **Structured Data**: Use lists, tables, and code blocks over prose
- **Fact Reporting**: Report facts and results, not internal thought processes
- **User Feedback Priority**: Treat user corrections as absolute requirements

### **Pine Script v6 Function Namespace Protocol**
- **Technical Analysis Functions**: Always use `ta.` prefix for technical analysis functions (e.g., `ta.atr()`, `ta.sma()`, `ta.ema()`)
- **Function Reference Validation**: Validate Pine Script function names and syntax before implementation
- **Namespace Compliance**: Ensure all technical analysis functions use correct Pine Script v6 namespace
- **Error Prevention**: Check function availability and syntax to prevent runtime errors
- **Documentation Reference**: Always reference official Pine Script v6 documentation for function names

### **Multi-Modal Filter Design Protocol**
- **Mode Selection**: Implement dropdown menus for complex filtering modes
- **Dynamic Calculation**: Create flexible threshold calculation functions based on selected mode
- **Parameter Organization**: Group related parameters logically with appropriate tooltips
- **User-Driven Design**: Use brainstorming sessions to improve feature design and user satisfaction
- **Flexible Implementation**: Design systems that can accommodate multiple approaches (Fixed, Dynamic, Statistical)

---

*This enhanced protocol integrates comprehensive MCP server knowledge to ensure institutional-grade Pine Script development with advanced trading methodology, clean code principles, and optimal performance.*

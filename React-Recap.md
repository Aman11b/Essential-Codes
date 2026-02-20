
 ## COMPONENTS
 * building block of UI
 * react renders the view of each component
 * component has its own data login and appearance
 * componenets can be reused nested inside and pass data between them



 ## component as function
 * 1->component name start with capital letter
 * 2->function needs to return some markup jsx or null
 * 3->each component returns exactly one element
 * 4->never nest component declaration


 ## JSX
 * -> declerative syntax to describe what component look like and how they work
 * -> each component retrun one block of JSX
 * -> extention of JS embed HTML + CSS and react
 * -> babel convert JSX(browser dont understand it) to JS
 * -> imperative approach (JS manually tell all to do)
 * -> declarative appraoch(just describe what ui should look like)


 ## React fragment
 * lets you add element without leaving trace in HTML tree so in DOM
 * just add <></> or <React.Fragment> thats it
 * sometimes key is required while rendering list
 * it allow more then one element inside JSX

 ## PROPS (PROPERTY)
 * ->passing data between components from parent to child components
 * ->first pass prop in component then receive it then
 * -> pass info down the tree
 * -> can pass any value in prop
 * -> props are ready-only => data in component is made from props (data coming from parent component basically outside)and state(internal component data that can be updated by logic basically inside)
 * -> props cant be modified by child component that are read only to mutate prop you need state
 * -> prop is obj if u change you change parent too and that cause side effect coz u are changing data which is outside ,react is pure function that means not affecting outside
 * -> one way data flow=> only from parent to child not opposite only top to bottom (not in angular) it makes application predictable and easier, debug becomes easy, two way data binding is less efficent

 ## RULES OF JSX
 * -> essestially HTML but with {can add JS code}
 * -> {statement are not allowed here like if else or for or switch}
 * -> JSX -> JS expression
 * -> a peace of JSX has on root element

 ## PROPS
 * -> props always exists in all components
 

 > StrictMode-> render twice in order to find bugs and check if outdated parts of API

 
 ## STATE
 * -> data a component can hold over time, ifo that component needs to remember though its life cycle
 * -> its kindoff memory that can be changed
 * -> state variable/peice of state a single variable in a component
 * -> state is an entrire condition at ant point of time > all peices ofm state together
 * -> updating state re-render component (one single component render its called a view all views together makes final UI)
 * -> with state react keep UI sync with data
 * ->useState retusn a array it takes defaut value and a function
 * -> useState is called hooks(but only in top level of function not in if or loop or something else)
 * ->dont update state manually
 * -> always term state as im-mutable and use setter function for updates

 ## mechanics of state
 * -> we dont manipulate state directly then how to update
 * -> react upadate conmpoenent view by completely rerending the component
 * -> react maintains a state which remain contant through the rerendering unless the component is removed from UI which is called un-mounting


 ## State vs Prop
 * -> state is internal data owned by component,component memory,can be updated by component itself,updating leads to rerendering ,used to make component interactive
 * -> props is external data owned by parent,read-only,when new prop is received re-rendering happens,used by parent to configure child component
 */


 ## THINKING IN REACT
 * -> break the desired UI into components and establish the component tree
 * -> build a static version
 * [state management]
 * -> think about state
 * - when to use state
 * - type os state logical or global
 * - where to place state
 * -> establish the data flow
 * - one way data flow
 * - parent to child communication
 * - accessing global state

 ## FUNDAMENTALE OF STATE MANAGEMENT
 * -> deciding when to create a peice of state what type of state are necessary where to place each peices of state and how data flows through the app
 * ->LOCAl STATE
 * - state needed only by one or few component
 * - alway start with local state
 * -> GLOBAL STATE (shared stae)
 * - state that many component might need
 * - implemented by content api or redux
 * -> WHEN and WHERE
 * -> need to store data( will this data change ? yes : regular variable) is can be computed then use previous existing state derived state > should it re-render component > no then REF (useRef, no re-render) > yes now create new state
 * -> WHERE
 * -> is needed in one component then leave it there
 * -> if can be needed in chalid component then pass it as props
 * -> if used by one or few sibling component -> left state to first commen parent (lifting state up)
 * -> if need in more sibilings then its global state


 ## LIFTING UP STATE
 * -> problem sharing state with sibliing component
 * -> lift it to closest common parent component
 * [data can only flow down to childen via props not sideways to siblings]
 * -> how a child promotion(child) update sate in checkout(parent) > pass setCoupon down to component which need to update the state


 ## DERIVED STATE
 * -> state that is computed from an existing peice of state or from props

## CHILDREN PROP
* -> an empty "hole" thta can be filled by any JSX the component receive as children
* -> insted of <button/> write more JSX <button>{here}</button> like html
* -> children of button,accessible through prop.children
* -> children prop allows us to pass JSX into a element
* -> essential tool to make resuable and configure component

## Prop Drilling
* -> whenever we are passing prop just so that it can reach to some other component and this one act as intermediate with no use of that prop

 ## HOW TO SPLIT UI IN COMPONENTS
 * -> Huge component
  - too many responsibility
  - might need too many props
  - hard to reuse
  - complex code,hard to undersatnd
 
  -> Small component
  - we will end up with 100s of mini components
  - confusing codebase
  - too abstracted
 
 * ->how to split
  - logical seperation
  - some are reusable
  - low complexity
 
 * -> 4 critrtia
  1. logical seperated of content/layout
     - does the conmponent contain peices of content or layout that dont't belong together?
     - is it possible to reuse part of this component?
     - do you want/need to reuse it?
     - is the component doing too many different things?
     - does the component reply on too many props?
     - does the component have too many peice of state and/or effect?
     - is the ocde ,including JSX ,too complex/confusing?
     - do you prefer smaller function/components?
     ### - If yes then you need a new component
 
  2. reusability
  3. responsibilities/complexity
  4. personal coding style
 
 ## GENERAL GUIDELINES
 * -> creating new component creates a new abstraction
 * -> name the component according to what it does or what it displays
 * -> never declare a new component inside another component
 * -> co-locate related components inside same file

## Component categories
 * -> stateless/presentational component
 * - no state
 * -receive prop and simpley present received data or other content
 * - usually small and reusable
 * -> stateful component
 * - have state
 * - can be reusable
 * -> structural component
 * - Pages, Layouts Screen or app
 * - esult of composition
 * - can be huge and non-reusable
 * - provide structure
  
 ## COMPONENT COMPOSITION
 * -> using a component inside a compoent dont let it to be reused
 * -> in component composition we pass children as a prop and now the component is reusable too
 * -> component composition is combining different compoent using the children prop (or explicitly defined props)
 * ->WE use component composition in 2 cases
 * - create highly reusable and flexible components
 * - fix a prop drilling (great for layouts)
 * - possible because components dont need to know their children in advance

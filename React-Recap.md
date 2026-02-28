
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

  ## COMPONENTS,INSTANCES,ELEMENTS
 * -> Components
 * - describe the UI
 * - component is a finction that retusn React element(element tree) ,usually written as JSX
 * - blueprint or template (using this component instances are created)
 * -> Instances
 * - instances are created when we use component
 * - instance is actual physical manifestation
 * - has its own state and prop
 * - has a lifecycle(can be born live and die)
 * -> Element
 * - as instances are executed react return a element
 * - JSX is converted to React.createElement() function call -> resulting react element
 * - it has all necessary info to create DOM element
 * COMPONENT (<Tab />) -> Component instances ( Returns) -> React Element (Inserted to DOM) -> DOM Element (HTML)

 ## $$typeof: Symbol(react.element)
 * -> this protects from cross site scripting attacts
 * -> Symbol are javaScript primitive which cant be trasnmitted via json
 * -> a symbol like this cant come from API call
   
```
console.log( <DifferentContent test={23} /> );
```
> this is type DifferentContent

```
console.log(DifferentContent());
```
> this is type div -> raw react element not component instances

## How rendering works > Overview
 * -> Reacp
 * - component -> component instances -> react element -> DOM Element -> UI
 * -> how react element change into DOM element
 * => How component are displayed on the screen
 * -> Render is triggered (by updating state somewhere) => Render Phase(react calls component finction and figure out how DOM should be updated) => Commit phase (React actaully writes to the DOM ,updating ,inserting nad deleting element) => Browser paint
 * -> in react ,rendering is NOT updating the DOM or displaying element on the screen.
 * -> Rendering only happens internally inside React,it does not produce visual changes

## How render are trigged
 * 1. Initial render of the application(when it runs for very first time)
 * 2. State is updated in one or more component instances(re-render)
 * -> render process is triggered for entire application
 * -> render are not triggred immediately, but scheduled for a when the JS engine has some " free time" (few miliseconds ).There is also batching of multiple setState calls in event handlers

## Review: Mechanics of state in react
* -> Not true #1: Rendering is updating the screen/dom (its calling component function )
* -> Not true #2: React completely discard old view(DOM) on re-render

 ## RENDER PHASE
 * 1. component instances that trigger re-render 
 * 2. react element
 * 3. new virtual DOM 
  - => VIRTUAL DOM (React element tree)
  - -> component tree -> react element tree(virtual DOM)
  - -> Virtual DOM: Tree of all react element created from all instances in the component tree
  - -> Cheap and fast to create multiple trees
  - -> nothing to do with Shadow DOM(brpwser technology used in web component)
  - -> in rerender new component tree is created and a new react element tree is creted
   ### Rendering a component will cause all of the child component to be rendered as well(no matter if porp changed or not) -> necessary because react doesn;t know weather children will be affected -> virtual DOM created again
* 4. Reconciliation + Diffing (Current fiber tree > before state update) 
  - its is done in react reconciler (Called Fiber)
  => WHat is reconsiliation and why do we need it?
  - creating react element tree is cheap and fast coz its just object but writing DOM is not is is relatively slow
  - usually only a small of DOM needs to be updated
  - react reuses as much of the exixtsing DOM as possible
  => how to know which DOM is changed -> reconciliation
  ### Reconciliation: Deciding which DOM elements actually need to be inserted ,deleted,or updated in order to reflect the latest state changes done by a reconciler(real engine of react current > reconciler is Fiber)
  => The Reconciler : Fiber
  - takes entire react element tree(virtual tree) -> (on initial render) -> creates Fiber tree
  ### Fiber Tree: internal tree that has a "fiber" for each component instance and DOM element
  - Fibers are not re-created on every render (its never destroyed just get mutated again and again over future reconciliation)
  (Fiber{"Unit of work"} -> (current state,Props,Side effects,Used Hooks,Queue of work,...))
  - each fiber is linked to it parent,all other has link to there previous sibling (linked list)
  - Virtual and Fiber tree has componet with DOM element too ,they are complete representaion of DOM structure
  - Work can be done asynchronously (Rendering process can be split into chunks,tasks can be prioritized,and work can be paused,reused or thrown away)
  -- enables conurrent feater like suspense or transitions starting react18
  --long render wont block JS engine
  => Reconciliation in Action
  - is there a a state update -> new virtual DOM is created-> new dom is reconcided + Diffing (Comparing elemtn based on there position in the tree is called diffing) with current fiber tree-> updated fiber tree(workInProgress tree) 
* 5. Updated Fiber tree
* 6. List of DOM updates => Result of the render phase ("list of effects"


  ## THE COMMIT PHASE AND BROWSER PAINT
 * 1. List of DOM update -> Update DOM
 * - React writes to the DOM: inserting ,deleting, and updates (list of DOM updates are "flushed" to the DOM)
 * - Committing is synchronous: DOM is updated in one go,it can't be interrupted.This is necessary so thta the DOM never shows partial result,ensuring a consistent UI(in sync with all times)
 * - after the commit phase is completes,the workInProgress fiber tree becomes the current tree for the next render cycle
 * (BROWSER PAINT)
 * 2. Updated UI on the screen
  > render phase (react) -> commit phase (ReactDOM) -> browser paint(browser)
  - react does not touch the DOM.react only renders.it doesnt know where the render result will go
  - react can be used on different platforms (Reactive Native -> iOS android, Remotion -> video, many more...)
 

## RECAP
 * 1. trigger(happen only on initila render or state update)
 * 2. render phase () -> updated react element-> new virtual DOM-> reconcilied and diffing with current fiber tree-> updated fiber tree -> list of DOM update
 * - do not pruduce any visual output
 * - rendering a component also renders all of its child component
 * - render is asynchronous: work can be split,prioritised ,paused and resumed
 * 3. Commit phase
 * - Updated DOM
 * - Synchronous : DOM update are written in on go ,to keep UI consistent
 * 4.Browser Paint (updated UI on screen)

## How Diffing works
 * -> 2 Fundamental Assumption
 * - Two element of different types will produce different trees
 * - Element with a stable key prop stay the same across renders
 * => this allowes reqact to go from O(n^3) to O(n) operations per 1000 element
 * -> its comparing element by element based on its position in tree
 * 1. Same position,different elelemt
 * - React assume entire sub-tree is no longer valid
 * - old component are destroyed and removed from DOM ,including state
 * - tree might be rebuilt if children stayed the same(state is reset)
 * 2. Same position ,same element
 * - element will be kept (as well as child element), including state
 * - sometimes this is not what we want.. then we can use key prop

  ## KEY PROP
 * -> special prop that we use to tell the diffing algo that an element is unique
 * -> allow react to distinguish between multiple instances of the same component type
 * -> when a key stays the same across renders,the elelemt will be kept in DOM(even if the position in the tree changes)
 * - using key in list
 * -> when a key chnages between render,the elelemt will be destroyed and a new one will be created (even if the position in the tree is the same as before)
 * - using key to reset the state
 * 1. KEYS IN LISTS (STABLE KEY)
 * -> no key-> adding a new list item -> same element ,but different position in tree,so they are removed and recreated in the DOM(bad for performance)
 * -> with keys -> adding new lits item ->different position in the tree but the key stays the same,so the element will be kept in DOM
 * 2. KEY PROP TO RESET STATE (CHANGING KEY)
 * -> if we have the same element at the same position in the tree the dom elelemt  and state will be kept
 * -> if we have a question component with a answer and we chnage the question the answer will remain the same and irrelevent in this case coz of the rule hnece use key so that its is differentiated and the sate will be reset

 ## TWO TYPES OF LOGIC IN REACT COMPONENT
 * 1.render logic
 * -> code that lives at the top level of th component function
 * -> participate in describing how the component view looks like
 * -> executed every time the component renders
 * 2.event handeling function
 * -> exexcuted as concequences of the event that the handler is listening for
 * -> code that actually does things
 
 ## FUNCTIONAL PROGRAMMING PRINCIPLES
 * 1.Side effect: dependency on or modification of any dat outside the function scope."Interration with outside world".Example: mutating external variable,HTTP request,Writing to DOM
 * 2.Pure function:a function that has no side effects
 * -> given the same input ,a pure function will always return the same output

 ## RULES FOR RENDER LOGIC
 * -> component must be pure when it comes to render login: given the same prop(input), a component instances should always return the same JSX (output)
 * -> render login must produce no sde effects: no interaction with the "outside world" is allwed.
 * So, in rende logic:
 * - Do not perform network request (API Calls)
 * - Do not start timer
 * - Do not directly use the DOM API
 * - Do not mutate object or variable outside of the function scope(This is why we cant mutate props)
 * - Do not uodate state(or Ref): this will create an infinite loop


 ## STATE UPDATE BATCHING
 * => How state update are batched
 * -> Render are not triggered immediately,but scheduled for when JS engine has some "free time".There is also bacthing of multiple setState call in event handlers
```
  const reset=fuction(){
   setAnswer("")
   console.log(answer)
   setBest(true)
   setSolved(false)
}
 ```
* -> it does not update state and render+ commit 3 times 
* -> all will be batched as one state update for entire event handler then redner+commit(just one render and commit per event handler)
* -> but what will be value of console.log 
* -> statee is stored in fiber tree during render phase 
* -> at this point,re-render has not happened yet
* -> therefore ,answer still containes current state,not the updated state(" ") -its is "Stale state"
* => that is why upadting state in react is asynchronous
* -> updated state variable are not immediately available after setState call,but only after the re-render
* -> this is also applies when only one state variable is updated
* -> if we need to update state based on previous update,we  use setState with call back(SetAnswer(answer=> ...))
* => Batching beyond event handler function
* -> automatic bathcing for event handler was in react 17 its for timeout and promises and native events too in react18+ 


 ## LIBRARY vs FRAMEWORK vs THE REACT ECOSYSTEM
 * -> Framework (all in one kit)
 * - everything you need to build a completed application is included in the framework("batteries included")
 * -> liberary (seperate ingredient)
 * - view library (react just draw component on UI)
 * - enternal library is needed
 

## Practical summary
 * -> a component is like a blueprint for a piece of UI that will eventually exist on the screen.When we "use" a component ,React create a component instance,which is like an actual physical manifestation of a component,containing prop,state na dmore. A component instance,when rendered,will return a React Element
 * -> Rendering only menas calling component function and calculating what DOM element need to be inserted deleted and updated.It has nothing to do with writing to DOM.Therefore each time a component instance is rendered and re-rendered the function is called again
 * -> only the initail app render and state update can cause a render,which happens for the entire application ,not just one single component
 * -> when a component instance gets re-rendered,all its children will get re-rendered as well.This doesnt mean that all children will get updated in the DOM,thanks to reconciliation ,whic checks which element hasve actually changed between two render.But all this re-rendereing can still have an impact on performance
 * -> diffing is how react decide which DOM element needs to be added or modified.If between render a certain react element stays at the same position in the element tree the corresponding DOM element and compoent state will saty the same.If the element changed to a different position of if it's a different element type the DOM element and state will be destroyed
 * -> giving element a key prop allow react to distinguish between multiple component instances.When a key stays the same across render,the element is kept in the DOM.This is why we need to use keys in list.When we chnage the key between reander the DOM element will be destroyed and rebuilt we use this as trick to reset state
 * -> never declare a new component inside another component,Doing so will re-create the nested component everytime the parent component re-render REqact will always see the nested component as new,and there reset its state each time the parent state is updated
 * -> the logic that produce JSX output for a component instances("render" logic) is not allowed to produce any side effect: no API calls no timer no object or variable mutation no state update. Side effect are allowed in event handler and userEffect
 * -> The DOM is udpated in the commit phase,but not by react but by a "renderer" called REACTDOM.Thats's why we always need to include both liberary in a react web app project. We can use other renderer to use react on different platforms for ep to built mobile or native apps
 * -> multiple state update inside an event handler function are batched so they happen all at once causing only one re-render.This means we can not access a state variable immediately after undating it: state udpate are asynchronous.Since react 18 batching also happens in timeout promises native and handlers
 * -> using event in event handlers we get access to a synthetic event object not the browser native object so that event work the same way across all browser.The difference is that most synthetic event bubble, including focus blur and chnage which do not bubble as native browser event. only the scroll vent does not bubble
 * -> react is a libery not a framework.This means that you can assemble your application using your favorite 3rd party liberary.The downside is that you need to find and learn all these additional liberies

## Component(instance) lifecycle
 * 1. Mounted/Initial render
 * - component instance is rendered for the first time
 * - fresh state and prop are created
 * 2. re-rendered(unlimited times)
 * - state change
 * - prop change
 * - parent change
 * - context change
 * 3. unmounted
 * - component instance is destoyed and removed
 * - state and prop are destroyed


## A First look at effect
 * -> Side effect is basically any interaction between a react component and the world outside the compnent
 * -> side effect should not happend in render logic
 * -> side effect can be implement by event handlers(function triggered) and effect(useEffect) - Effect allow us to write code that will run at different moment:Mount re-ender or un-mount



## Event handler
 * - executed when the corresponding event happens
 * - use to react to an event
 * - preferred way to create side effects
 * Effect
 * - executed after the component mount(initial mount) and after subsequent re-render(accourding to dependency array)
 * - each one has Effect code + Cleanup function + dependency array
 * - used to keep a component synchronized with some external system
  

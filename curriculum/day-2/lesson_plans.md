# Lesson Plans

## Required Knowledge

- idea of functions as first class citizens 
- components and props
- importing other components
    - maybe from within folders (index.js with the name of the folder being what gets imported)
- values rendered within components
- using className on elements (dont use class)

## Plan
1. create and setup the project from the beginning (https://github.com/jlarmstrongiv/tracecamp-winter-2020/blob/main/reference/setting_up_a_project.md)
    1. make folder `live-code`
    2. initilize using `npx create-next-app`
    3. add tailwind with `npm install tailwindcss postcss`
        1. `postcss.config.js` and populate
        2. `tailwind.css` and populate
            1. remove other css files in `styles` folder
        3. add tailwind line to `_app.js`
    4. move source content to a `src` folder
        1. eveything except `.next` and `node_modules`
2. add a div that centers all content on the page, so that everyone can see any changes I make to content on the page
3. 

## Topics (Key-points)

### hooks

- allow us to make our site interactive
- taping into what is called the lifecycle of the components we make
    - mounting
    - updating, via looking for changes
        - when the something on the component has changed and needs to be updated visualy
    - unmounting
- The rules of hooks
    - when you can use a hook
        - within a function component (in the outermost scope)
        - within a custom hook (in the scope of another function)
    - when you cannot use a hook
        - within a conditional

### useState

- store values on the page that are persistant between page renders
- useState function returns a list of two values
    - the value that the useState holds
    - and a function that allows use to change the value stored
        - can take a new value
        - or can take a function that returns a new value, with the first argument being the current state
- only change the value through the function
    - if not then the page will not rerender when the value changes
- **lists** `const [list, setList] = useState([])`
    - appending a value: `setList([...list, new_value])`
    - removing a value (using *filter* or *slice*)
- **objects** `const [obj, setObj] = useState({})`
    - *add*/*change* property: `setObj({...obj, key: value})`

### useEffect

- cause something to happen as a response to change in the component (this can be state or a definition)
- second parameter is an optional list of what to respond to
    - `* nothing *`: runs on every re-render
    - `[]`: runs when the component is mounted
    - `[value]`: runs when `value` changes (shallowly, objects get remade every render)
- you can return a function from the first parameter function that gets called whenever the first effect needs to be cleaned up
    - for `[]`: occurs when the component unmounts
    - for `[value]`: occurs after the value has changed once the effect is run at least once

### Forms

- value component is the
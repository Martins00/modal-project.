This is file i am using to take notes of tyhe things i am learning instead of writing them down in my book

1> Node modules
    This sis where any libraries or dependencies are stored. whenever we install anything new, it goes there.
2> Public
    This contains the index.html file that has been initially sent to the browser
3> src
    We write our Css and js inside the src. we write our templates and components here
    The js that kickstart the app is here.

In a typical vue component, we have the template, scipt and the style.

//Template refs:
    We use this in selecting somethung from the dom.
    We use the dollar sign to call refs. i.e when we give the ref of an element a name, we use the $refs. When we want to call it, we use;
    this.$refs.theNammeWeGaveToTheRefForThatElement.whaterverWeWantToDo

To import a vue app into the primary/parent vue, we must first import it a,d then put it inside the cpmponentss object before putting it in the twmplate tag.
When we put it in the template tag, we are going to be using the name we gave it in the component as our element/tag name.  

Make sure you do not give your vue app the name of a preexisiting element. At the very least, just use Capital letter for the
first letter.

Adding "scoped" to the style tag in a vue component will keep it there in that it will not affect any other component.
Another way is to make the selector more specific. like li.h1{desired style}.
Whenever there is a global file that we need to import, we do it in the main.js file bys simply using:
import "file path" 
It is best to create Vue components to start with capital letters, So you o=don't end up mixing up the names with a regular html element.
If both names should conflict, it would lead to a problem even tho i cannot ecaxtly remember what the would be. 

//Props
 We can pass in props in  the element that is named after our vue components.
 for instance; say we named our element "modal", we'd have;
 <modal header="This is my first prop" text="This is my second prop" />
 the props above are header and text. to use them, we go into the modal.vue and in the script. export defualt, we create a new 
 component named props which will be an array. It is in this array that we would put the header and text. 
 This is done to avoid hard coding. Making it more dynamic. So it can be used in other part of the website.
 It is best to put the value of the props down in the data component rather than put it in thr element tag. 
 So in the element, what we would have is binding the props. i.e;
 :header='header' :text='text'. Do not forget that the actual content is being stored in the data component.

 //Custom Events
 The $emit, is used by the child component, to send a message to a parent component, to fire a particular acction/function.
 whatever name you put in the bracket for tge funvtion is what you would use to receive that function in the parent component.
 click modifiers can be triggered by puttin a . after the @click
 Using @click.self, you are telling that action to only fire when the click is specifically on it. I will not work on any other element even if they are within it.

 //Slots
 They are meant to pass templates into components and not data, unlike props.
 To use slots, we put the content of the slot between the component tag in the app.vue
 for instance, we are working on the Modal app. So, we put the content of the slot in between the modal 
 tag, then add a "slot" element, in the modal.vue.
 We can either use the default slot or the named slots.
 To use the named slot, we have to put a template tag within the Modal element in the app.vue component. Otherwise, it will 
 just go to the normal slot tag in the midal.vue component.
 WHen we use a named slot, we have to apply a directive called 'v-slot:anythingWeNameIt'. Note that this will not make it show yet.
 To make it show, We have to create another slot tag and input the name we gave that slot here. WE PUT THE NAME BY DOING;
 <slot name="anythingWeNameIt"></slot>. This qould make it display on the page as a slot.
 This helps us structure the modal just the way we want it.

 //Teleport
 If we want to render our modal in some other div, what we do is that we use the teleport element in the component instead of div.





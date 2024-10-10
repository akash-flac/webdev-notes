# Context API
- To avoid prop drilling, React introduced Context API.
- Prop Drilling : To pass the props to a certain child component of the application, the parent component needs to pass down the props to every child component between itself and the target child component. This is prop drilling. The intermediate child components didn't even need those props but just to pass them down, they have to take them.
- Using Context API, one can define their state variables outside the component tree. 
- (https://github.com/100xdevs-cohort-2/week-7) ![](attachments/Pasted%20image%2020240911211449.png)
- 3 Steps:
	- Define the context in a separate file.
	- Provide the context throughout the component chain.
	- `useContext` hook can be used to get the current value of the state variable.
- ![](attachments/Pasted%20image%2020240911211653.png)
- Problem with Context API : Even the components which do not contain the state variables are re-rendered. This is why we use state management libraries like Recoil. Context API only helps in getting rid of prop drilling and writing a cleaner code, but the rendering is not more performant.

# Recoil
- A state management library for React

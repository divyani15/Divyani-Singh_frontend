1. Explain what the simple List component does.
Ans: The List component in this code displays a list of items passed to it as a prop. It renders a list of items in an unordered list format. Each item in the list is represented by an '<li>' element. The background color of the '<li>' element depends on whether it is currently selected or not.
The List component also defines a function called handleClick that updates the selected index of the clicked item in the parent WrappedListComponent. This function is passed as a prop to each SingleListItem component and is called whenever an item is clicked.

The List component uses the useState hook to define the selectedIndex state and the useEffect hook to reset the selectedIndex state to null whenever the items prop changes. This ensures that if the items in the list change, the selected index is reset and no item is selected by default.
To optimize performance, the WrappedListComponent and SingleListItem components are memoized using the memo higher-order component. This prevents unnecessary re-renders when the props of these components do not change.


2. What problems / warnings are there with code?
Ans:There are several issues in this code that need to be addressed for it to work correctly.

Firstly, in the WrappedListComponent, the useState hook is called incorrectly with selectedIndex as the setter and setSelectedIndex as the state value. This should be corrected to [selectedIndex, setSelectedIndex].
Secondly, in the SingleListItem component, the isSelected prop is not used correctly to determine the background color. Instead, it should be compared with the index of the current item.
Thirdly, the items prop type in WrappedListComponent is defined using PropTypes.array instead of PropTypes.arrayOf. The defaultProps for items should be set to an empty array instead of null.
Fourthly, in the SingleListItem component, the onClickHandler function is not called properly. To avoid it being called immediately on rendering, it should be wrapped in arrow function.
Addressing these issues will ensure that the code works correctly and renders a list of items with the correct background color for the selected item.

3. For the modified code,refer 'app.js'!
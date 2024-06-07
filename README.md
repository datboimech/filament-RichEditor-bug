This repo will go over the Forms\Components\RichEditor::make('') bug.

This problem only occurs when(the packages of composer and npm are update to the lastest) and the individual has changed the MarkdownEditor to RichEditor and switches the "Create Post" method to the slideover action.  

*to create the bug*

1. slideover:
    - https://github.com/datboimech/filament-description-bug/blob/83e6aed3566e928176ec4db8a300be976be5d9b2/app/Filament/Resources/Blog/PostResource/Pages/ListPosts.php#L16

2. Replace MarkdownEditor with RichEditor:
    - https://github.com/datboimech/filament-description-bug/blob/83e6aed3566e928176ec4db8a300be976be5d9b2/app/Filament/Resources/Blog/PostResource.php#L58

3. You must comment out the "'create' => Pages\CreatePost::route('/create'),":
    - https://github.com/datboimech/filament-description-bug/blob/83e6aed3566e928176ec4db8a300be976be5d9b2/app/Filament/Resources/Blog/PostResource.php#L253

(This problem will be set on the post section on the demo website) 
When using the RichEditor for slideover to create a post; after filling the form out on the demo. When the person clicks the "Create & Create Another" button. The text in RichEditor will stay after the button is clicked.

+ Screenshots
Before:
![image](https://github.com/datboimech/filament-description-bug/assets/47047103/c0fc683b-fe13-4455-a4e8-5f9b88ee0a49)
Look at the title on the table

After:
![image](https://github.com/datboimech/filament-description-bug/assets/47047103/c7579785-e834-450f-8915-3b8d87ec8271)
The text doesn't clear after the "Create & Create Another" button

Last problem to the bug; if you copy and paste the text in the same place then save, it will not save into the post.

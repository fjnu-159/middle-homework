# middle-homework159wzl

期中实验：记事本功能扩展

一、实验内容

1.实现记事本的时间戳功能。

2.实现记事本的搜索功能。

3.根据个人能力实现记事本的扩展功能。

二、作品展示

1.实现记事本的时间戳功能。

2.实现记事本的搜索功能（依据记事本标题和正文内容进行模糊搜索）。

3.实现记事本正文缩略显示。

![实现时间戳和正文缩略显示](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/timewrite.png)

![实现了根据标题和正文进行模糊搜索](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/Search.png)

三、代码解析

1.时间戳功能的实现。

（1）修改noteslist_item.xml代码新增显示时间戳的组件。

![noteslist_item.xml](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/timeXml.png)

（2）修改NotePadProvider中的insert方法。

![NotePadProvider](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/providerInsert.png)

（3）修改NoteEditor中的updateNote方法。

![NoteEditor](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/editorUpdateNote.png)

（4）修改NotesList中的PROJECTION（添加笔记那一行是正文缩略）。

![NotesList](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/NotesListPROJECT.png)

（5）修改NoteList中的dataColums与viewIDs（添加的是NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE与R.id.text2第三个是正文缩略）。

![dataAndview](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/dataAndview.png)

2.搜索功能的实现。

（1）修改list_options_menu.xml增加搜索组件。

![searchXml](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/searchXml.png)

（2）在NoteList中的onCreateOptionsMenu方法中添加搜索监听器。

![实现搜索功能关键代码](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/searchJAVA.png)

mSearchView.setOnQueryTextListener设置监听器

onQueryTextSubmit当搜索框的文本提交时调用此函数，由于我们的搜索要求是实时的，所以不管它。

onQueryTextChange当搜索框的文本改变时调用此函数，正好符合我们的要求。我们需要在这里重新写一个cursor和adapter。

3.正文缩略显示功能的实现。

（1）修改noteslist_item.xml代码新增显示正文缩略的组件。

![noteslist_item.xml](https://github.com/fjnu-159/middle-homework159wzl/blob/master/picture/writeXml.png)

（3）修改NotesList中的PROJECTION（截图见修改时间戳（4））。

（4）修改NoteList中的dataColums与viewIDs（截图及详情见时间戳（5））。

四、总结

1.时间戳和正文缩略显示原理相同，且正文缩略比较简单。

2.实现搜索功能其实不需要增加一个搜索类这么麻烦，只要增加一个监听器就可以了。

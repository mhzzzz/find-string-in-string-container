# find-string-in-string-container
P314-ex9_28

Write a function that takes a forward_list and two additional string arguments. The function should find the first string and insert the second immediately following the first. If the first string is not found, then insert the second string at the end of the list.

    void find_and_insert(forward_list<string> &list, string const& to_find, string const& to_add)
    {
     auto prev = list.before_begin();
     for (auto curr = list.begin(); curr != list.end(); prev = curr++)
        {
         if (*curr == to_find)
            {
                list.insert_after(curr, to_add);
                return;
            }
        }
        list.insert_after(prev, to_add);
    }
    
    from pexy_______________________________
    ________________________________________
    void func(forward_list<string> &flst, const string& to_find, const string& to_add)
    {
	    auto pre = flst.before_begin();
	    auto curr = flst.begin();
	    for(auto curr = flst.begin(); curr != flst.end(); curr++){
		    if(*curr == to_find)
			    flst.insert_after(curr, to_add);
			    return ;
		    else
			    pre = curr; 
			    //第一个string没有，才在flst末尾插入第二个string
			    //应该在for循环结束后执行插入第二个string。 
	    }
	    flst.insert_after(pre, to_add);
	    //此时curr = flst.end(),因此pre刚好指向flst的最后一个元素
	    //在pre后插入第二个string。 
    } 

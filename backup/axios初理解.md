1. 响应拦截器的response处理200-299的响应码，其他的由error处理
2. 响应拦截器返回response.data，其实就是后端返回的数据，里面一般包括三个部分，code，message，data
3. 如果由pinia的actions中的函数对response.data进行处理，即根据code进行判断，这里是业务类型的响应码处理
4. axios的error其类型是AxiosError，而业务类型的error一般直接使用内置Error，要注意它们内部的属性是不一样的，前者是error.response，response里面可能还有其他数据，后者是error.message
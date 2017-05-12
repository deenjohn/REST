
#### req.params.bookId

**defines the /Books/:bookId route**

bookRouter.route('/Books/:bookId')
    .get(function(req,res){

       
        Book.findById(req.params.bookId, function(err,book){
            if(err)
                res.status(500).send(err);
            else
                res.json(book);
        });
    });

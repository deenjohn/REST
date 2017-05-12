
bookRouter.route('/Books')
    .get(function(req,res){

            var query = {};
            //this will allow us to filter by only genre

           // res.send('get /books/');

           //http://localhost:3000/api/Books?genre=Science Fiction
            if(req.query.genre)
            {
                query.genre = req.query.genre;
            }

            
           
            Book.find(query,function(err,books){
                if(err)
                    res.status(500).send(err);
                else{
                    
                    res.json(books);
                }
            });
          
            

      });

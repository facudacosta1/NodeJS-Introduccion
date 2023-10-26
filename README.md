# CRUD BÁSICO CON NODEJS

Para trabajar en este proyecto deberás realizar lo siguiente:
1- Abre la terminal y ejecuta el comando `npm install`, el cual instalará todas las dependencias del proyecto. Sin este paso no podrás trabajar.
2- A continuación ejecuta el comando `npm run dev`, el cual inicia el servidor en "modo desarrollo" utilizando nodemon.
3- Puedes comenzar a trabajar en app.js y realizar lo solicitado.

##Solución 

app.put("/people/:index", (req, res) => {
  /* COMPLETA EL CÓDIGO NECESARIO:
     Para que se pueda actualizar el objeto asociado al índice indicado en la URL 
   */

     const index = req.params.index;
     if(index<0||index>= people.length){
      res.status(404).json({error: "Indice inválido"});
     } else {
      people[index] = req.body;
      res.json(people[index]);
     }
});

app.delete("/people/:index", (req, res) => {
  /* COMPLETA EL CÓDIGO NECESARIO:
     Para que se pueda eliminar el objeto asociado al índice indicado en la URL 
   */

     const index = req.params.index;
     if(index<0||index>= people.length){
      res.status(400).json({error: "índica invalido"});
     }else{
      const deletedPerson = people.splice(index,1);
      res.json(deletedPerson[0]);
     }
});

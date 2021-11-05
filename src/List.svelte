<script>
let todoList = [{id: 1, post: "Work"}, {id: 2, post: "Sleep"},];
let count = 3;
let message = "";
let handleChange = (event) => {
    message = event.target.value;
}
let handleSubmit = () => {
    if(message.trim().length !== 0 ){
    todoList = [...todoList, {id: count, post: message}];
    count += 1;
    message = "";}
}
</script>
<main>
    <div class="box" id="heading">
        <h1>To-do List </h1>
    </div>
    
    
    
    <div class="box">
        

            {#each todoList as item }
                <div class="item">
                    <input type="button" class="tick" value="✔️" on:click={()=>{
                    let list = todoList.filter((in_post)=>{
                        if(in_post.id !== item.id) return true;
                        else return false;
                      });
                    
                     todoList = list;
                    }}>
                    <p> {item.post} </p>
                </div>
                <!-- <input type="hidden" name="listName"> -->
            {/each}

            <form action="/" method="post" class="item">
            <input type="text" name="newItem" placeholder="New Item" value={message} autocomplete="off" on:change={handleChange}>
            <button type="submit" name="list" value="todo" on:click|preventDefault ={handleSubmit}>+</button></form>
        
    </div>

</main>

<style>
    #heading {
        padding: 2px;
        width: 25vw;
  background-color: #A683E3;
  text-align: center;
}
.box {
  max-width: 400px;
  margin: 50px auto;
  background: white;
  border-radius: 5px;
  box-shadow: 5px 5px 15px -5px rgba(0, 0, 0, 0.3);
}

.item {
  min-height: 70px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #F1F1F1;
}
.item {
  min-height: 70px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #F1F1F1;
}

.item:last-child {
  border-bottom: 0;
}

/* input:checked+p {
  text-decoration: line-through;
  text-decoration-color: #A683E3;
} */

input[type="button"] {
  margin: 20px;
  background-color: #fff;
  border: 0;

}

p {
  margin: 0;
  padding: 20px;
  font-size: 20px;
  font-weight: 200;
  color: #00204a;
}


button {
  min-height: 50px;
  min-width: 60px;
  border-radius: 50%;
  border-color: transparent;
  background-color: #A683E3;
  color: #fff;
  font-size: 30px;
  padding-bottom: 12px;
  margin-top: 4%;
  border-width: 0;
}

input[type="text"] {
  text-align: center;
  height: 60px;
  top: 10px;
  border: none;
  background: transparent;
  font-size: 20px;
  font-weight: 200;
  width: 290px;
  margin-left: 30px;
  margin-right: 10px;
}

input[type="text"]:focus {
  outline: none;
  box-shadow: inset 0 -3px 0 0 #A683E3;
}

::placeholder {
  color: grey;
  opacity: 1;
}

</style>


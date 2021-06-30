<script>
    import { firestore } from "../db";
     


    async function getData() {
		const response = await firestore.collection('users').doc('user1').get();
		console.log(response.data());
	}

    async function createData(){
        await firestore.collection('users').add({
            name : 'puri',
            branch: 'CSE',
            rollno: 592
        });
        console.log("successfully created");
    }

    async function updateData(){

        await firestore.collection('users').doc('user2').update({
            name :'k.jayanthi'
        });
        console.log("sucessfully updated");

    }

    async function delData(){
        await firestore.collection('users').doc('user3').delete();
        console.log("successfully delted");
    }

</script>

<button on:click={getData}>get Data</button>
<button on:click={createData}>create Data</button>
<button on:click={updateData}>update data</button>
<button on:click={delData}>del data</button>

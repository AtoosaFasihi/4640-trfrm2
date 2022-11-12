# 4640-trfrm2

##To replicate the configuration on a new machine follow these instructions: 
* clone the ripo on the same directory
* Your file structure should look similar to the picture bellow:

![tree](https://user-images.githubusercontent.com/71790429/201448070-b95703ed-ac83-42d3-ab4a-90c7de397eea.JPG)

# Configure Terraform 

* create a new API token on Digitalocean 
* create a .env file in the dev directory 
* copy your token and save it to the .env file (`export TF_VAR_do_token=<my API tocken>`)
* source your .env file by running 

```source .env```

* you can check the validation of the main.tf file by running `terraform validate`(in the dev directory)

![terraform-validate](https://user-images.githubusercontent.com/71790429/201447840-59d0622b-fc16-46bd-8a46-79fe86e6eab8.JPG)

* After the configuration is valid you can run `terraform plan` to see what will be created using terraform.

* To apply all the changes simply run `terraform apply` which will apply all the changes configured in the main.tf file. 

# Configure Ansible
* create a file in the dev directory called "do_token"
* copy the same token from last step and save it to the do_token file (`export DO_API_TOKEN=<my API tocken>`)
* source the do_token file by running 
```source do_token```

* For checking the ansible inventory graph run 
``` ansible-inventory --graph ```

![ansible](https://user-images.githubusercontent.com/71790429/201448697-5b6f2fe2-9fb6-4747-bb95-52d87cb3d1f5.JPG)

* To test the ansible set up run 
``` ansible -m ping -u root all ```

![ping](https://user-images.githubusercontent.com/71790429/201448877-d50c0bb1-258c-40c0-b206-42ec1cfdff2f.JPG)

* To run the playbook run

```  ansible-playbook nginx_setup.yml -u root ```

![playbook](https://user-images.githubusercontent.com/71790429/201448995-306d306e-4b1a-4aee-9ad7-06d5d9fb2308.JPG)

* To check if everything works correctly go to the loadbalancer's IP address and you should see the nginx page as shown below:

![nginx](https://user-images.githubusercontent.com/71790429/201449074-8ccb5e92-a450-450d-8d2b-1fcac0958c33.JPG)




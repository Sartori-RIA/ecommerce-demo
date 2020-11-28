# Ecommerce

## Setup

+ ENV
    + RUN `cp config/application.yml.example config/application.yml`

+ DOCKER
    + RUN `docker-compose up -d`
    + RUN `docker exec -it ecommerce_api /bin/bash`
    
+ DEPENDENCIES
    + RUN `bundle`
    + NVM
        + RUN `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash`
        + exit and back to container
        + RUN `nvm install node`
        + exit and back to container  
        + RUN `npm i -g yarn`
    + RUN `yarn`
    
+ DATABASE
    + RUN `rails db:create`
    + RUN `rails db:migrate`
    + RUN `rails db:seed`
    + RUN `rails spree_sample:load`

+ GET API KEY
    + RUN `rails c`
    + RUN `Spree::User.find_by_email('admin@example.com').try(:spree_api_key)`

+ START SERVER
    + RUN `rails s -b=0.0.0.0`

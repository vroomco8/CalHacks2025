# VotEZ

**Contributors** : Varun Chakka, Sathvik Lingaram, Iha Gadiya, Shlok Powar

<img width="200" height="570" alt="image" src="https://github.com/user-attachments/assets/ef7ab9c5-dcc5-457a-bcc1-9899b9305522" />
<img width="200" height="570" alt="image" src="https://github.com/user-attachments/assets/820ad598-baa6-4437-b13b-a66ddf100e26" />
<img width="200" height="570" alt="image" src="https://github.com/user-attachments/assets/f0996e5f-c4a6-4c8d-aeee-69b437252830" />
<img width="200" height="570" alt="image" src="https://github.com/user-attachments/assets/58d9d845-a1a8-4c76-88dc-088b852e7e51" />

## Inspiration 💡

During 2024, our group turned 18, during peak election season. This means that we had gained the ability to vote. However, getting thrown into a massive storm of information getting spewed out left and right gets confusing real fast. With the amount of propositions, candidates, and agendas that were getting pushed onto us, it was easy to get overwhelmed by the amount of information. So we thought: what if we could have an app simplify everything for us? 

## What it does 📄

votEZ scrapes the web for the current running candidates for presidents, vice presidents, and governors for every state. It scrapes their agendas and using that information, simplifies it into a short passage that summarizes everything for the user with as little bias as possible. Another feature is that it scrapes the web for propositions and simplifies them into paragraphs and also gives potential outcomes to the proposition.

## How we built it 🛠️

For the backend, we built a CRUD system using **python Flask API** and **gunicorn** to handle http request handling, routing, and database management. Using python concurrently, we were able to run the backend server at the same time we ran the frontend script. For scraping, we used python **BeautifulSoup** to scrap ballotopedia.org and built multiple .csv files (which we then converted to json) to train our AI model. Using **GroqAPI**, we made multiple chatbots: a general overview, and a specific chatbot that will help the user out with what is on the current page. Additionally, GroqAPI was used to simplify the data on screen so that it would not take as much space on mobile compared to web. Groq was also used to translate languages on screen, so we can switch Using the **Expo Router** and **React Native**, we were able to build a concurrent mobile and web application. We used supabase for authentification and user/chat history.

## Challenges we ran into 🖋️
One of the biggest challenges we ran into was trying to host our backend server. Initially, our chatbot and scraping would only work on web because our code was based on localhost, meaning we needed a server. Initially, we had to run 3+ terminals to run the backend and the frontend for the mobile application to work (we had no idea why). Until we stumbled upon gunicorn and concurrently, which helped run both the backend and frontend server easily and also fixed our problem with mobile.

Another problem that we had was with scraping. With web scraping with beautiful soup, we noticed a pattern that the scraper would always fail to fetch unless the website was already opened beforehand. Initially, we were considering to use selenium in order to open a headless browser with the sites to scrape. However, due to time, we just decided to compile all the data we can using the scrape with the time we had left and train the Groq model with that. Therefore, we had to only display data from 2022-2024 time periods as there is no current widespread election cycle data for 2026.

## What's next for votEZ 📈
Currently, votEZ is only built around state governors, vice presidents, and presidents for previous years. Due to lack of time, we were not able to gather more data (such as county, district, boards, etc.) Additionally adding more accessibility features such as text-to-speech and voice input would have made the chatbot a lot more interactive. Since this towards people that do not have experience or resources whether that be due to time constraints or impoverished backgrounds, we aim to guide them through this process, one step at a time.



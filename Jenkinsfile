node {
stage ('Deploy') {
   sh 'ssh -p2244 pkbot@pkbotnode rm -rf /home/pkbot/pkbot'
   sh 'ssh -p2244 pkbot@pkbotnode git clone -b master https://github.com/vishnu4b3/pkbot.git'
  sleep 30
   sh 'ssh -p2244 pkbot@pkbotnode cd /home/pkbot/pkbot'
  sleep 10
   sh 'ssh -p2244 pkbot@pkbotnode docker build -t hubotimage /home/pkbot/pkbot/'
 sleep 30 
   sh 'ssh -p2244 pkbot@pkbotnode docker volume create hubotvolume'
  sleep 10
   sh 'ssh -p2244 pkbot@pkbotnode docker run -itd -p 6379 --name hubot -v hubotvolume:/home/hubot/pkbot hubotimage'
		    }
}

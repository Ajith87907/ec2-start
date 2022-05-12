pipelines {
  agent any
    
    stages {
	stage("stop/start_instance") {

	properties([parameters([string(defaultValue: 'i-09d9a399dffe744c0', description: 'enter instance id', name: 'InstanceID'), choice(choices: ['Start', 'Stop'], description: 'state', name: 'State')])])
	
		
	   steps {
		
		sh'''

			if [ "$State" = "Start" ] 
			then 
 			aws ec2 start-instances --instance-ids $InstanceID 
  			echo Instance $InstanceID Started
 
			elif [ "$State" = "Stop" ] 
			then 
  			aws ec2 stop-instances --instance-ids $InstanceID 
  			echo Instance $InstanceID Stopped 
			fi 
		'''

	          }
		}
	     }
           }

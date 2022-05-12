pipeline {
	agent any 
	parameters {
        string(name: 'InstanceID', defaultValue: 'i-09d9a399dffe744c0', description: 'instanceid')
	choice(name: 'State', choices: ['Start', 'Stop'], description: 'Pick something')
    }
    stages {

	stage("stop/start_instance") {
		
	   steps {
		
		sh"""

			if [ "$State" = "Start" ] 
			then 
 			aws ec2 start-instances --instance-ids $InstanceID 
  			echo Instance $InstanceID Started
 
			elif [ "$State" = "Stop" ] 
			then 
  			aws ec2 stop-instances --instance-ids $InstanceID 
  			echo Instance $InstanceID Stopped 
			fi 
		"""

	             }
	       }
	 }
}

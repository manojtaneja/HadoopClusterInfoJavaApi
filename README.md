# HadoopClusterInfoJavaApi
This java api's will help you getting any type of cluster information i.e either the cloudera managed cluster
or Ambari managed Hortonworks or Big insights or normal Hadoop cluster or a Mapr one.

Version 1 of this util jar will bring in the information from Ambari based cluster for hortonworks or big insights but surely the wrok for cloudera manager
and Map r is in progress and will be updated in subsequent versions.

SAMPLE CODE :

public class AmbariHandler {

	
	
	public static void main(String args[]) {
		RootConnection Impl = new AmbariRestImpl();
		Impl.getConnectionObject("irl63ppd10", 8080, "admin", "admin");
		String clustername = Impl.getClusterName();
		String tag = Impl.getdesiredConfigTAG(clustername, "hive-site");
		System.out.println("Value is"
				+ Impl.getactualConfigurationkeyvalue(clustername, "hive-site",
						tag, "hive.zookeeper.client.port"));
		System.out.println("Properties list  is"
				+ Impl.getactualConfigurationproperties(clustername,
						"hive-site", tag));
	}
	
	}
	
	public class ClouderaHandler {

	
	
	public static void main(String args[]) {
		RootConnection Impl = new ClouderRestImpl();
		Impl.getConnectionObject("irl63ppd10", 8080, "admin", "admin");
		String clustername = Impl.getClusterName();
		String tag = Impl.getdesiredConfigTAG(clustername, "hive-site");
		System.out.println("Value is"
				+ Impl.getactualConfigurationkeyvalue(clustername, "hive-site",
						tag, "hive.zookeeper.client.port"));
		System.out.println("Properties list  is"
				+ Impl.getactualConfigurationproperties(clustername,
						"hive-site", tag));
	}
	
	}

	

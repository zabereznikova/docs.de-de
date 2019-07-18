---
title: Erweitern des Hosting mit ServiceHostFactory
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: e553fe161ffc5b50850d916cf1cef6b38dd5c1a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991314"
---
# <a name="extending-hosting-using-servicehostfactory"></a>Erweitern des Hosting mit ServiceHostFactory
Der Standard <xref:System.ServiceModel.ServiceHost> -API für das Hosten von Diensten in Windows Communication Foundation (WCF) ist ein Erweiterungspunkt, in der WCF-Architektur. Benutzer können ihre eigenen Hostklassen von <xref:System.ServiceModel.ServiceHost> ableiten, üblicherweise um <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> für die Verwendung von <xref:System.ServiceModel.Description.ServiceDescription> zu überschreiben, um Endpunkte imperativ hinzuzufügen oder das Verhalten vor dem Öffnen des Diensts zu ändern.  
  
 In der selbst gehosteten Umgebung müssen Sie keine benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse erstellen, weil Sie den Code schreiben, der den Host instantiiert, und rufen anschließend <xref:System.ServiceModel.ICommunicationObject.Open> für den Host auf. Zwischen diesen beiden Schritten können Sie beliebige Vorgänge ausführen. Sie könnten z.&amp;#160;B. ein neues <xref:System.ServiceModel.Description.IServiceBehavior> hinzufügen:  
  
```  
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 Dieser Ansatz ist nicht wiederverwendbar. Der Code, der die Beschreibung bearbeitet, wird in das Hostprogramm eingefügt (in diesem Fall in die Main()-Funktion), daher ist es schwierig, diese Logik in anderen Kontexten wiederzuverwenden. Es gibt auch andere Wege, ein <xref:System.ServiceModel.Description.IServiceBehavior> hinzuzufügen, die keinen imperativen Code erfordern. Sie können von <xref:System.ServiceModel.ServiceBehaviorAttribute> ein Attribut ableiten und es in Ihren Dienstimplementierungstyp aufnehmen, oder Sie können ein benutzerdefiniertes Verhalten konfigurierbar gestalten und es dynamisch mithilfe einer Konfiguration erstellen.  
  
 Es kann jedoch auch eine kleine Variante des Beispiels verwendet werden, um dieses Problem zu lösen. Ein Ansatz besteht darin, den Code, mit dem ServiceBehavior hinzugefügt wird, von `Main()` in die <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>-Methode einer benutzerdefinierten Ableitung von <xref:System.ServiceModel.ServiceHost> zu verschieben:  
  
```  
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 Dann können Sie innerhalb von `Main()` Folgendes verwenden.  
  
```  
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 Sie haben jetzt die benutzerdefinierte Logik in einer abstrakten Form gekapselt, die so in verschiedenen Hostimplementierungen wiederverwendet werden kann.  
  
 Es ist nicht unmittelbar einsichtig, wie diese benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse innerhalb von IIS (Internetinformationsdiensten) oder WAS (Windows Process Activation Service) verwendet werden kann. Diese Umgebungen unterscheiden sich von einer selbst gehosteten Umgebung, weil die Hostumgebung im Namen der Anwendung <xref:System.ServiceModel.ServiceHost> instantiiert. Die Hostumgebungen IIS und WAS wissen jedoch nichts von Ihrer benutzerdefinierten <xref:System.ServiceModel.ServiceHost>-Ableitung.  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory> wurde dafür konzipiert, dieses Problem des Zugriffs auf Ihre benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse durch IIS oder WAS zu lösen. Da ein benutzerdefinierter, von <xref:System.ServiceModel.ServiceHost> abgeleiteter Host dynamisch konfiguriert und von potentiell unterschiedlichem Typ ist, wird er von der Hostumgebung niemals direkt instantiiert. Stattdessen verwendet WCF ein Factorymuster, um eine Schicht der Dereferenzierung zwischen der hostumgebung und dem konkreten Typ des Diensts bereitzustellen. Sofern Sie nichts anderes angeben, wird dazu eine Standardimplementierung von <xref:System.ServiceModel.Activation.ServiceHostFactory> verwendet, die eine Instanz von <xref:System.ServiceModel.ServiceHost> zurückgibt. Aber Sie bieten auch eine eigene Factory, die den abgeleiteten Host zurückgibt, durch Angabe der CLR-Typnamen Ihrer Factoryimplementierung in der @ServiceHost Richtlinie.  
  
 Ziel ist, dass in den grundlegenden Fällen die Implementierung einer eigenen Factory eine einfache Angelegenheit sein sollte. Als Beispiel folgt hier eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory>, die eine abgeleitete <xref:System.ServiceModel.ServiceHost>-Klasse zurückgibt:  
  
```  
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 Um diese Factory statt der standardfactory verwenden möchten, geben Sie den Namen in der @ServiceHost Richtlinie wie folgt:  
  
```  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Zwar gibt es keine technische Grenze für das, was Sie mit einer von <xref:System.ServiceModel.ServiceHost> zurückgegebenen <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>-Klasse tun können, jedoch wird empfohlen, die Implementierung der Factory so einfach wie möglich zu halten. Falls Sie benutzerdefinierte Logik großen Umfangs definieren müssen, platzieren Sie sie statt in die Factory besser in den Host, damit der Code einfacher wiederverwendet werden kann.  
  
 Es gibt noch eine weitere Ebene der Host-API, die hier erwähnt werden muss. WCF verfügt auch über <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, von dem <xref:System.ServiceModel.ServiceHost> und <xref:System.ServiceModel.Activation.ServiceHostFactory> abgeleitet. Diese sind für erweiterte Szenarien vorgesehen, in denen Sie große Teile des Metadatensystems mit Ihren benutzerdefinierten Klassen auslagern müssen.

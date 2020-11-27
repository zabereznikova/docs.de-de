---
title: Erweitern des Hosting mit ServiceHostFactory
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: d2224ea683326679efdad368cf2ff7b2b95f4dba
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273125"
---
# <a name="extending-hosting-using-servicehostfactory"></a>Erweitern des Hosting mit ServiceHostFactory

Die Standard- <xref:System.ServiceModel.ServiceHost> API für Hostingdienste in Windows Communication Foundation (WCF) ist ein Erweiterbarkeits Punkt in der WCF-Architektur. Benutzer können ihre eigenen Hostklassen von <xref:System.ServiceModel.ServiceHost> ableiten, üblicherweise um <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> für die Verwendung von <xref:System.ServiceModel.Description.ServiceDescription> zu überschreiben, um Endpunkte imperativ hinzuzufügen oder das Verhalten vor dem Öffnen des Diensts zu ändern.  
  
 In der selbst gehosteten Umgebung müssen Sie keine benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse erstellen, weil Sie den Code schreiben, der den Host instantiiert, und rufen anschließend <xref:System.ServiceModel.ICommunicationObject.Open> für den Host auf. Zwischen diesen beiden Schritten können Sie beliebige Vorgänge ausführen. Sie könnten z.&#160;B. ein neues <xref:System.ServiceModel.Description.IServiceBehavior> hinzufügen:  
  
```csharp
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
  
```csharp
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
  
```csharp
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 Sie haben jetzt die benutzerdefinierte Logik in einer abstrakten Form gekapselt, die so in verschiedenen Hostimplementierungen wiederverwendet werden kann.  
  
 Es ist nicht unmittelbar einsichtig, wie diese benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse innerhalb von IIS (Internetinformationsdiensten) oder WAS (Windows Process Activation Service) verwendet werden kann. Diese Umgebungen unterscheiden sich von einer selbst gehosteten Umgebung, weil die Hostumgebung im Namen der Anwendung <xref:System.ServiceModel.ServiceHost> instantiiert. Die Hostumgebungen IIS und WAS wissen jedoch nichts von Ihrer benutzerdefinierten <xref:System.ServiceModel.ServiceHost>-Ableitung.  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory> wurde dafür konzipiert, dieses Problem des Zugriffs auf Ihre benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse durch IIS oder WAS zu lösen. Da ein benutzerdefinierter, von <xref:System.ServiceModel.ServiceHost> abgeleiteter Host dynamisch konfiguriert und von potentiell unterschiedlichem Typ ist, wird er von der Hostumgebung niemals direkt instantiiert. Stattdessen verwendet WCF ein Factorymuster, um eine Dereferenzierungsschicht zwischen der Host Umgebung und dem konkreten Typ des Diensts bereitzustellen. Sofern Sie nichts anderes angeben, wird dazu eine Standardimplementierung von <xref:System.ServiceModel.Activation.ServiceHostFactory> verwendet, die eine Instanz von <xref:System.ServiceModel.ServiceHost> zurückgibt. Sie können jedoch auch eine eigene Factory bereitstellen, die den abgeleiteten Host zurückgibt, indem Sie den CLR-Typnamen Ihrer Factory-Implementierung in der- @ServiceHost Direktive angeben.  
  
 Ziel ist, dass in den grundlegenden Fällen die Implementierung einer eigenen Factory eine einfache Angelegenheit sein sollte. Als Beispiel folgt hier eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory>, die eine abgeleitete <xref:System.ServiceModel.ServiceHost>-Klasse zurückgibt:  
  
```csharp
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 Wenn Sie diese Factory anstelle der Standardfactory verwenden möchten, geben Sie den Typnamen in der- @ServiceHost Direktive wie folgt an:  
  
`<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>`  
  
 Zwar gibt es keine technische Grenze für das, was Sie mit einer von <xref:System.ServiceModel.ServiceHost> zurückgegebenen <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>-Klasse tun können, jedoch wird empfohlen, die Implementierung der Factory so einfach wie möglich zu halten. Wenn Sie über viele benutzerdefinierte Logik verfügen, ist es besser, diese Logik in Ihrem Host anstatt innerhalb der Factory zu platzieren, damit Sie wieder verwendet werden kann.  
  
 Es gibt noch eine weitere Ebene der Host-API, die hier erwähnt werden muss. WCF verfügt auch über <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.Activation.ServiceHostFactoryBase> , von <xref:System.ServiceModel.ServiceHost> denen <xref:System.ServiceModel.Activation.ServiceHostFactory> bzw. abgeleitet werden. Diese sind für erweiterte Szenarien vorgesehen, in denen Sie große Teile des Metadatensystems mit Ihren benutzerdefinierten Klassen auslagern müssen.

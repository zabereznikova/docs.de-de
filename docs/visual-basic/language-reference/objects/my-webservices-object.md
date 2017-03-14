---
title: "My.WebServices Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.WebServices"
  - "My.MyProject.WebServices"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.WebServices object"
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# My.WebServices Object
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Enthält Eigenschaften, mit denen eine Einzelinstanz jedes XML\-Webdiensts, mit dem das aktuelle Projekt verbunden ist, erstellt werden oder auf diese Einzelinstanz zugegriffen werden kann.  
  
## Hinweise  
 Das `My.WebServices`\-Objekt stellt eine Instanz von jedem Webdienst bereit, auf den im aktuellen Projekt verwiesen wird.  Jede Instanz wird bei Bedarf instanziiert.  Sie können auf diese Webdienste über die Eigenschaften des `My.WebServices`\-Objekts zugreifen.  Der Name der Eigenschaft ist identisch mit dem Namen des Webdienstes, auf den die Eigenschaft zugreift.  Jede Klasse, die von <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> erbt, ist ein Webdienst.  Informationen über das Hinzufügen von Webdiensten zu einem Projekt finden Sie unter [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Das `My.WebServices`\-Objekt macht nur die dem aktuellen Projekt zugeordneten Webdienste verfügbar.  Es ermöglicht nicht den Zugriff auf Webdienste, die in DLLs deklariert sind, auf die verwiesen wird.  Um auf einen Webdienst zuzugreifen, der von einer DLL bereitgestellt wird, müssen Sie den qualifizierten Namen des Webdiensts im Format *DLL\-Name*.*Webdienstname* verwenden.  Weitere Informationen finden Sie unter [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Das Objekt und seine Eigenschaften sind für Webanwendungen nicht verfügbar.  
  
## Eigenschaften  
 Jede Eigenschaft des `My.WebServices`\-Objekts ermöglicht den Zugriff auf eine Instanz eines Webdienstes, auf die das aktuelle Projekt verweist.  Der Name der Eigenschaft stimmt mit dem Namen des Webdienstes überein, auf den die Eigenschaft zugreift, und der Eigenschaftentyp stimmt mit dem Typ des Webdienstes überein.  
  
> [!NOTE]
>  Wenn ein Namenskonflikt besteht, lautet der Eigenschaftenname für den Zugriff auf einen Webdienst *Stammnamespace*\_*Namespace*\_*Dienstname*.  Stellen Sie sich beispielsweise zwei Webdienste mit dem Namen `Service1` vor.  Wenn sich einer dieser Dienste im Stammnamespace `WindowsApplication1` und im Namespace `Namespace1` befindet, rufen Sie den Dienst über `My.WebServices.WindowsApplication1_Namespace1_Service1` auf.  
  
 Beim ersten Zugriff auf eine der Eigenschaften des `My.WebServices`\-Objekts erstellt die Eigenschaft eine neue Instanz des Webdienstes und speichert diese.  Bei anschließenden Zugriffen auf diese Eigenschaft wird diese Instanz des Webdienstes zurückgegeben.  
  
 Sie können einen Webdienst freigeben, indem Sie der Eigenschaft für diesen Webdienst `Nothing` zuweisen.  Der Eigenschaftensetter weist dem gespeicherten Wert `Nothing` zu.  Wenn Sie der Eigenschaft einen anderen Wert als `Nothing` zuweisen, löst der Setter eine <xref:System.ArgumentException>\-Ausnahme aus.  
  
 Mit dem Operator `Is` oder dem Operator `IsNot` können Sie überprüfen, ob eine Eigenschaft des `My.WebServices`\-Objekts eines Instanz des Webdienstes speichert.  Sie können mit diesen Operatoren überprüfen, ob der Wert der Eigenschaft `Nothing` ist.  
  
> [!NOTE]
>  Normalerweise muss der Operator `Is` oder der Operator `IsNot` den Wert der Eigenschaft lesen, um den Vergleich durchzuführen..  Wenn die Eigenschaft gegenwärtig jedoch `Nothing` speichert, erstellt sie eine neue Instanz des Webdienstes und gibt dann diese Instanz zurück.  Der Visual Basic\-Compiler behandelt aber die Eigenschaften des `My.WebServices`\-Objekts auf besondere Weise und lässt das Überprüfen des Status der Eigenschaft durch den Operator `Is` oder den Operator `IsNot` ohne eine Änderung ihres Werts zu.  
  
## Beispiel  
 In diesem Beispiel wird die `FahrenheitToCelsius`\-Methode des `TemperatureConverter`\-XML\-Webdienstes aufgerufen und das Ergebnis zurückgegeben.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 Damit dieses Beispiel ausgeführt werden kann, muss das Projekt auf den Webdienst `Converter` verweisen, und dieser Webdienst muss die `ConvertTemperature`\-Methode verfügbar machen.  Weitere Informationen finden Sie unter [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Dieser Code kann in einem Webanwendungsprojekt nicht ausgeführt werden.  
  
## Anforderungen  
  
### Verfügbarkeit nach Projekttyp  
  
|||  
|-|-|  
|Projekttyp|Verfügbar|  
|Windows\-Anwendung|**Ja**|  
|Klassenbibliothek|**Ja**|  
|Konsolenanwendung|**Ja**|  
|Windows\-Steuerelementbibliothek|**Ja**|  
|Web\-Steuerelementbibliothek|**Ja**|  
|Windows\-Dienst|**Ja**|  
|Website|Nein|  
  
## Siehe auch  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>   
 <xref:System.ArgumentException>   
 [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
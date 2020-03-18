---
title: Verwalten von Verbindungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
ms.openlocfilehash: 11c17c6893800fce8bbff8f49b3a207c161bcdfa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047646"
---
# <a name="managing-connections"></a>Verwalten von Verbindungen
Anwendungen, die HTTP zum Herstellen einer Verbindung mit Datenressourcen verwenden, können die <xref:System.Net.ServicePoint>- und <xref:System.Net.ServicePointManager>-Klassen von .NET Framework verwenden, um Verbindungen mit dem Internet zu verwalten und dabei zu helfen, dass diese eine optimale Skalierung und Leistung erreichen.  
  
 Die **ServicePoint**-Klasse stellt eine Anwendung mit einem Endpunkt bereit, mit der sich die Anwendung verbinden kann, um auf Internetressourcen zuzugreifen. Jede **ServicePoint**-Klasse enthält Informationen, die dabei helfen, Verbindungen mit einem Internetserver zu optimieren, indem Optimierungsinformationen zwischen Verbindungen geteilt werden, um die Leistung zu verbessern.  
  
 Jede **ServicePoint**-Klasse wird durch einen URI (Uniform Resource Identifier) identifiziert und gemäß dem Schemabezeichner und Hostfragmenten des URI kategorisiert. Beispielsweise würde die gleiche **ServicePoint**-Instanz Anforderungen für die URIs `http://www.contoso.com/index.htm` und `http://www.contoso.com/news.htm?date=today` bereitstellen, da sie über den gleichen Schemabezeichner (HTTP) und die gleichen Hostfragmente (`www.contoso.com`) verfügen. Wenn die Anwendung bereits über eine persistente Verbindung mit dem Server `www.contoso.com` verfügt, ruft sie über diese Verbindung beide Anforderungen ab, wobei vermieden wird, dass zwei Verbindungen erstellt werden müssen.  
  
 **ServicePointManager** ist eine statische Klasse, die die Erstellung und Zerstörung von **ServicePoint**-Instanzen verwaltet. Die **ServicePointManager**-Klasse erstellt eine **ServicePoint**-Klasse, wenn die Anwendung eine Internetressource anfordert, die nicht in der Auflistung der vorhandenen **ServicePoint**-Instanzen enthalten ist. **ServicePoint**-Instanzen werden zerstört, wenn sie die maximale Leerlaufzeit überschritten haben oder wenn die Anzahl der vorhandenen **ServicePoint**-Instanzen die maximale Anzahl von **ServicePoint**-Instanzen für die Anwendung überschreitet. Sie können sowohl die maximale Standardleerlaufzeit als auch die maximale Anzahl von **ServicePoint**-Instanzen steuern, indem Sie die <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A>- und <xref:System.Net.ServicePointManager.MaxServicePoints%2A>-Eigenschaften für die **ServicePointManager**-Klasse festlegen.  
  
 Die Anzahl der Verbindungen zwischen einem Client und einem Server kann sich drastisch auf den Anwendungsdurchsatz auswirken. Standardmäßig verwendet eine Anwendung, die die <xref:System.Net.HttpWebRequest>-Klasse verwendet, maximal zwei persistente Verbindungen. Sie können die maximale Anzahl von Verbindungen jedoch je nach Anwendung festlegen.  
  
> [!NOTE]
> Die HTTP/1.1-Spezifikation beschränkt die Anzahl der Verbindungen von einer Anwendung auf zwei Verbindungen pro Server.  
  
 Die optimale Anzahl von Verbindungen hängt von den tatsächlichen Bedingungen ab, unter denen die Anwendung ausgeführt wird. Das Erhöhen der Anzahl der verfügbaren Verbindungen für die Anwendung wirkt sich möglicherweise nicht auf die Leistung der Anwendung aus. Um zu ermitteln, wie sich mehr Verbindungen auswirken, führen Sie Leistungstests durch, wobei Sie die Anzahl von Verbindungen variieren. Sie können die Anzahl der Verbindungen ändern, die von einer Anwendung verwendet werden, indem Sie, wie im folgenden Codebeispiel gezeigt, die statische <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>-Eigenschaft für die **ServicePointManager**-Klasse bei der Anwendungsinitialisierung ändern.  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 Das Ändern der **ServicePointManager.DefaultConnectionLimit**-Eigenschaft wirkt sich nicht auf zuvor initialisierte **ServicePoint**-Instanzen aus. Der folgende Code zeigt das Ändern der Verbindungsbeschränkung für eine vorhandene **ServicePoint**-Klasse für den Server `http://www.contoso.com` in den in `newLimit` gespeicherten Wert.  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Connection Grouping (Verbindungsgruppierung)](connection-grouping.md)
- [Using Application Protocols (Verwenden von Anwendungsprotokollen)](using-application-protocols.md)

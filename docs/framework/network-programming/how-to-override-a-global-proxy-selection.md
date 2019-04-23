---
title: 'Vorgehensweise: Überschreiben einer globalen Proxyauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: f822aa18b6eecaa1b1302ad6cc6b94f0b016e330
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127373"
---
# <a name="how-to-override-a-global-proxy-selection"></a>Vorgehensweise: Überschreiben einer globalen Proxyauswahl
In diesem Beispiel wird an `www.contoso.com` eine **WebRequest** gesendet, die die globale Proxyauswahl mit einem Proxyserver namens `alternateproxy` auf Port 80 überschreibt.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   [`using`-Anweisung](~/docs/csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)
- [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

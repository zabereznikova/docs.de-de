---
title: 'Gewusst wie: Überschreiben einer globalen Proxyauswahl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2be271123e34f155a79269d3b810c50fe24a40c6
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48849931"
---
# <a name="how-to-override-a-global-proxy-selection"></a>Gewusst wie: Überschreiben einer globalen Proxyauswahl
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
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)  
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

---
title: 'Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 99bbff5a3350f55f04fdbd6ce7147b6597773322
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624587"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation
In diesem Beispiel wird eine globale Proxyinstanz erstellt, die es jedem <xref:System.Net.WebRequest> ermöglicht, einen Proxy zu verwenden, um mit dem Internet zu kommunizieren. Im Beispiel wird davon ausgegangen, dass der Proxyserver `webproxy` heißt und auf Port 80 kommuniziert, dem Standard-HTTP-Port.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- [`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) für den **System.Net**-Namespace  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)
- [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

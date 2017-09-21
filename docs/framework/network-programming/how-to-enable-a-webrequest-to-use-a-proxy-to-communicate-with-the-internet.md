---
title: "Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys für die Internetkommunikation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a42b9f947f4c3d59c3e17a892e4db405e2bc8b64
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys für die Internetkommunikation
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
  
-   Verweise auf den Namespace **System.Net**  
  
## <a name="see-also"></a>Siehe auch  
 [Using Application Protocols (Verwenden von Anwendungsprotokollen)](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Accessing the Internet Through a Proxy (Zugreifen auf das Internet über einen Proxy)](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)


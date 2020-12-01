---
title: 'Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 86ad862dbff9f4a982eec27a6806bcbb6c16f3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255805"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Gewusst wie: Registrieren eines benutzerdefinierten Protokolls mit WebRequest

In diesem Beispiel wird gezeigt, wie Sie eine protokollspezifische Klasse registrieren, die an anderer Stelle definiert ist. In diesem Beispiel stellt `CustomWebRequestCreator` das vom Benutzer implementierte Objekt dar, das die **Create**-Methode implementiert, die wiederum das `CustomWebRequest`-Objekt zurückgibt. Im Codebeispiel wird vorausgesetzt, dass Sie den `CustomWebRequest`-Code geschrieben haben, der das benutzerdefinierte Protokoll implementiert.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Dieses Beispiel erfordert Folgendes:  
  
 Verweise auf den Namespace <xref:System.Net>  
  
## <a name="see-also"></a>Weitere Informationen

- [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](programming-pluggable-protocols.md)

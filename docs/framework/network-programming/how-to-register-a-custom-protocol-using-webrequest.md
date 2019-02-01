---
title: 'Vorgehensweise: Registrieren eines benutzerdefinierten Protokolls mit WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: d2056bee6c8847989556799511dfaea326dcdac1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669041"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Vorgehensweise: Registrieren eines benutzerdefinierten Protokolls mit WebRequest
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
 Für dieses Beispiel benötigen Sie Folgendes:  
  
 Verweise auf den Namespace <xref:System.Net>  
  
## <a name="see-also"></a>Siehe auch
- [Programmieren austauschbarer Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md)

---
title: 'Gewusst wie: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 30006e43899cb146f02dbed3e8e72ed1b5416f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Gewusst wie: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream
In diesem Beispiel erfahren Sie, wie Sie eine Webseite anfordern und die Ergebnisse als Stream abrufen.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Namespaces <xref:System.IO> und <xref:System.Net>.  
  
## <a name="see-also"></a>Siehe auch  
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)

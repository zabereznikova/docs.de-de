---
title: 'Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 74cb739d381c0b1422d9277be8c3c338a46f8fba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647419"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream
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
  
- Verweise auf die Namespaces <xref:System.IO> und <xref:System.Net>.  
  
## <a name="see-also"></a>Siehe auch

- [Requesting Data (Anfordern von Daten)](../../../docs/framework/network-programming/requesting-data.md)

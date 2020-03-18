---
title: 'Gewusst wie: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 65bda268cd77959dbcd786c365d0a30c324b89ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71393109"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Gewusst wie: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream

In diesem Beispiel erfahren Sie, wie Sie eine Webseite anfordern und die Ergebnisse als Stream abrufen.
  
## <a name="example"></a>Beispiel

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

 Dieses Beispiel erfordert Folgendes:

- Verweise auf die Namespaces <xref:System.IO> und <xref:System.Net>.

## <a name="see-also"></a>Weitere Informationen

- [Anfordern von Daten](requesting-data.md)

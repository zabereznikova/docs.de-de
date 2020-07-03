---
title: 'Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream'
description: In diesem Beispiel erfahren Sie, wie Sie eine Webseite anfordern und die Ergebnisse als Stream im .NET Framework abrufen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: bd57f9af6be29c783d044e785ebb36aaa8592df2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502482"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream

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

 Für dieses Beispiel benötigen Sie Folgendes:

- Verweise auf die Namespaces <xref:System.IO> und <xref:System.Net>.

## <a name="see-also"></a>Siehe auch

- [Requesting Data (Anfordern von Daten)](requesting-data.md)

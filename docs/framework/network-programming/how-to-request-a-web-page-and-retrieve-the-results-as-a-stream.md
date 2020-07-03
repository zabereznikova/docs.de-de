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
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="344a5-103">Vorgehensweise: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream</span><span class="sxs-lookup"><span data-stu-id="344a5-103">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="344a5-104">In diesem Beispiel erfahren Sie, wie Sie eine Webseite anfordern und die Ergebnisse als Stream abrufen.</span><span class="sxs-lookup"><span data-stu-id="344a5-104">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="344a5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="344a5-105">Example</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="344a5-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="344a5-106">Compiling the Code</span></span>

 <span data-ttu-id="344a5-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="344a5-107">This example requires:</span></span>

- <span data-ttu-id="344a5-108">Verweise auf die Namespaces <xref:System.IO> und <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="344a5-108">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="344a5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="344a5-109">See also</span></span>

- [<span data-ttu-id="344a5-110">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="344a5-110">Requesting Data</span></span>](requesting-data.md)

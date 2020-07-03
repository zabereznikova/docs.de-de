---
title: 'Vorgehensweise: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht'
description: Hier erfahren Sie, wie Sie eine protokollspezifische WebResponse-Klasse abrufen, die einer WebRequest-Klasse im .NET Framework entspricht.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 15b1912a7bd951df7f3c14eb96251c2bdf237b4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502456"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a>Vorgehensweise: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht
In diesem Beispiel erfahren Sie, wie Sie ein protokollspezifisches WebResponse abrufen, das einem WebRequest entspricht.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf den Namespace **System.Net**  
  
## <a name="see-also"></a>Siehe auch

- [Requesting Data (Anfordern von Daten)](requesting-data.md)

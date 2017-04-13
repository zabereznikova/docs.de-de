---
title: "Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht
Dieses Beispiel zeigt, wie ein protokollspezifisches WebResponse abruft, das ein WebRequest übereinstimmt.  
  
## Beispiel  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf **System.Net**\-Namespace.  
  
## Siehe auch  
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)
---
title: "Nicht unterst&#252;tzte Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Nicht unterst&#252;tzte Funktionen
In LINQ to SQL können die folgenden SQL\-Funktionen nicht durch Übersetzung von vorhandenen CLR\- und .NET Framework\-Konstrukten genutzt werden:  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Obwohl `LIKE` nicht durch direkte Übersetzung unterstützt wird, ist eine ähnliche Funktionalität in der <xref:System.Data.Linq.SqlClient.SqlMethods>\-Klasse vorhanden.  Weitere Informationen finden Sie unter [M:System.Data.Linq.SqlClient.SqlMethods.Like\(System.String,System.String](assetId:///M:System.Data.Linq.SqlClient.SqlMethods.Like(System.String,System.String?qualifyHint=True&autoUpgrade=True).  
  
-   `DATEDIFF`  
  
     LINQ to SQL unterstützt `DATEDIFF` nur eingeschränkt.  Ähnliche Funktionalität ist in der [SqlMethods](assetId:///T:System.Data.Linq.SqlClient.SqlMethods?qualifyHint=False&autoUpgrade=True)\-Klasse vorhanden.  
  
-   `ROUND`  
  
     LINQ to SQL unterstützt `ROUND` nur eingeschränkt.  Weitere Informationen finden Sie unter [System.Math\-Methoden](../Topic/System.Math%20Methods.md).  
  
## Siehe auch  
 [Datentypen und Funktionen](../Topic/Data%20Types%20and%20Functions.md)
---
title: "Friend assembly reference &lt;reference&gt; is invalid | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31535"
  - "bc31535"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31535"
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Friend assembly reference &lt;reference&gt; is invalid
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der Friend\-Assemblyverweis "\<Verweis\>" ist ungültig.Mit starken Namen signierte Assemblys müssen einen öffentlichen Schlüssel in ihren InternalsVisibleTo\-Deklarationen angeben.  
  
 Durch den an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>\-Attributkonstruktor übergebenen Assemblynamen wird eine Assembly mit starkem Namen angegeben, diese enthält jedoch kein `PublicKey`\-Attribut.  
  
 **Fehler\-ID:** BC31535  
  
### So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie den öffentlichen Schlüssel für die Friend\-Assembly mit starkem Namen.  Schließen Sie den öffentlichen Schlüssel als Teil des Assemblynamens ein, der mithilfe des `PublicKey`\-Attributs an den <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>\-Attributkonstruktor übergeben wird.  
  
## Siehe auch  
 <xref:System.Reflection.AssemblyName>   
 [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Erstellen von signierten Friend\-Assemblys](../Topic/How%20to:%20Create%20Signed%20Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)
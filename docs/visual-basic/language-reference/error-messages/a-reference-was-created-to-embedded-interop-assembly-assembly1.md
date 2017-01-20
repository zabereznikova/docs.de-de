---
title: "A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39; | Microsoft Docs"
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
  - "vbc40059"
  - "bc40059"
helpviewer_keywords: 
  - "VBC40059"
  - "BC40059"
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Es wurde ein Verweis auf die eingebettete Interopassembly "\<Assembly1\>" aufgrund eines indirekten Verweises auf diese Assembly aus Assembly "\<Assembly2\>" erstellt.Es kann ratsam sein, die Eigenschaft "Interoptypen einbetten" in einer Assembly zu ändern.  
  
 Sie haben einen Verweis auf eine Assembly \(assembly1\) hinzugefügt, deren `True`\-Eigenschaft auf `Embed Interop Types` festgelegt ist.  Dadurch wird der Compiler angewiesen, Interoptypinformationen von dieser Assembly einzubetten.  Der Compiler kann jedoch keine Interoptypinformationen von dieser Assembly einbetten, da eine andere Assembly, auf die verwiesen wird \(assembly2\), ebenfalls auf diese Assembly verweist \(assembly1\) und die `False`\-Eigenschaft auf `Embed Interop Types` festgelegt ist.  
  
> [!NOTE]
>  Das Festlegen der `Embed Interop Types`\-Eigenschaft in einem Assemblyverweis auf `True` entspricht dem Verweisen auf die Assembly mit der `/link`\-Option für den Befehlszeilencompiler.  
  
 **Fehler\-ID:** BC40059  
  
### So reagieren Sie auf diese Warnung  
  
-   Um Interoptypinformationen für beide Assemblys einzubetten, legen Sie die `Embed Interop Types`\-Eigenschaft in allen Verweisen auf assembly1 auf `True` fest.  
  
-   Um die Warnung zu entfernen, können Sie die `Embed Interop Types`\-Eigenschaft von assembly1 auf `False` festlegen.  In diesem Fall werden Interoptypinformationen von einer primären Interopassembly \(PIA\) bereitgestellt.  
  
## Siehe auch  
 [\/link](../../../visual-basic/reference/command-line-compiler/link.md)   
 [Programming with Primary Interop Assemblies](http://msdn.microsoft.com/de-de/306fa1d6-0703-4004-9e93-d0a57f1be81e)
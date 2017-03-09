---
title: "/moduleassemblyname | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "moduleassemblyname compiler option [Visual Basic]"
  - "/moduleassemblyname compiler option [Visual Basic]"
  - "-moduleassemblyname compiler option [Visual Basic]"
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /moduleassemblyname
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt den Namen der Assembly an, die dieses Modul beinhalten wird.  
  
## Syntax  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`assembly_name`|Der Name der Assembly, die dieses Modul beinhalten wird.|  
  
## Hinweise  
 Der Compiler verarbeitet die `/moduleassemblyname`\-Option nur, wenn die Option `/target:module` angegeben wurde.  Dies bewirkt, dass der Compiler ein Modul erstellt.  Das vom Compiler erstellte Modul ist nur für die Assembly gültig, die mit der `/moduleassemblyname`\-Option angegeben wird.  Wenn Sie das Modul in einer anderen Assembly einfügen, treten Laufzeitfehler auf.  
  
 Die `/moduleassemblyname`\-Option ist nur dann erforderlich, wenn die folgenden Bedingungen erfüllt sind:  
  
-   Ein Datentyp im Modul benötigt Zugriff auf einen `Friend`\-Typ in einer referenzierten Assembly.  
  
-   Die referenzierte Assembly hat der Assembly, die aus dem Modul erstellt wird, Friend\-Assemblyzugriff gewährt.  
  
 Weitere Informationen zum Erstellen eines Moduls finden Sie unter [\/target](../../../visual-basic/reference/command-line-compiler/target.md).  Weitere Informationen zu Friend\-Assemblys finden Sie unter [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
> [!NOTE]
>  Die `/moduleassemblyname`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur beim Kompilieren über die Eingabeaufforderung.  
  
## Siehe auch  
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../Topic/How%20to:%20Build%20a%20Multifile%20Assembly.md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)
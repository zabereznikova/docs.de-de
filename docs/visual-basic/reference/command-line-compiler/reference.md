---
title: "/reference (Visual Basic) | Microsoft Docs"
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
  - "/reference compiler option [Visual Basic]"
  - "r compiler option [Visual Basic]"
  - "-reference compiler option [Visual Basic]"
  - "/r compiler option [Visual Basic]"
  - "reference compiler option [Visual Basic]"
  - "-r compiler option [Visual Basic]"
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /reference (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bewirkt, dass der Compiler dem Projekt, das Sie gerade kompilieren, Typinformationen in den angegebenen Assemblys bereitstellt.  
  
## Syntax  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`fileList`|Erforderlich.  Durch Kommas getrennte Liste von Assemblydateinamen.  Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ein.|  
  
## Hinweise  
 Die Dateien, die Sie importieren, müssen Assembly\-Metadaten enthalten.  Außerhalb der Assembly sind nur `Public`\-Typen sichtbar.  Die [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)\-Option importiert Metadaten aus einem Modul.  
  
 Wenn auf eine Assembly verwiesen wird \(Assembly A\), die ihrerseits auf eine weitere Assembly verweist \(Assembly B\), müssen Sie in folgenden Fällen auf Assembly B verweisen:  
  
-   Ein für Assembly A verwendeter Typ erbt von einem Typ oder implementiert eine Schnittstelle von Assembly B.  
  
-   Ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode mit einem Rückgabe\- oder Parametertyp aus Assembly B wird aufgerufen.  
  
 Geben Sie mithilfe von [\/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) das Verzeichnis an, in dem sich ein oder mehrere Assemblyverweise befinden.  
  
 Damit der Compiler einen Typ in einer Assembly \(nicht in einem Modul\) erkennt, muss er gezwungen werden, den Typ aufzulösen.  Eine mögliche Lösung hierfür besteht z. B. darin, eine Instanz des Typs zu definieren.  Es gibt noch andere Möglichkeiten, die Auflösung der Typennamen in einer Assembly für den Compiler zu erzwingen.  Bei Vererbung eines Typs in einer Assembly erfährt der Compiler den Typennamen.  
  
 Standardmäßig wird die Antwortdatei "Vbc.rsp" verwendet, die auf häufig verwendete [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Assemblys verweist.  Verwenden Sie `/noconfig`, wenn der Compiler die Datei Vbc.rsp nicht verwenden soll.  
  
 `/r` ist die Kurzform von `/reference` .  
  
## Beispiel  
 Im folgenden Code wird die Quelldatei I`nput.vb` kompiliert und auf Assemblys in M`etad1.dll` und M`etad2.dll` verwiesen, um O`ut.exe` zu erstellen.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
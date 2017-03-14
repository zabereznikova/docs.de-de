---
title: "Documenting Your Code with XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "XML, documenting code"
  - "XML comments, Visual Basic"
  - "Visual Basic code, documenting with XML"
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Documenting Your Code with XML (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können Sie den Code mit XML dokumentieren.  
  
## XML\-Dokumentationskommentare  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erleichtert die automatische Erstellung der XML\-Dokumentation für Projekte.  Sie können für die Typen und Member automatisch ein XML\-Skelett generieren und anschließend Zusammenfassungen, eine erläuternde Dokumentation zu jedem Parameter und weitere Hinweise bereitstellen.  Mit der entsprechenden Konfiguration wird die XML\-Dokumentation automatisch in eine XML\-Datei ausgegeben, die den gleichen Namen wie das Projekt und die Erweiterung XML hat.  Weitere Informationen finden Sie unter [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 Die XML\-Datei kann verwendet werden oder als XML\-Code bearbeitet werden.  Diese Datei befindet sich in demselben Verzeichnis wie die ausgegebene EXE\- oder DLL\-Datei des Projekts.  
  
 Die XML\-Dokumentation beginnt mit `'''`.  Die Verarbeitung dieser Kommentare unterliegt einigen Beschränkungen:  
  
-   Die Dokumentation muss regelkonformes XML aufweisen.  Falls der XML\-Code nicht regelkonform ist, wird eine Warnung ausgegeben und ein Kommentar in die Dokumentation eingefügt, dass ein Fehler aufgetreten ist.  
  
-   Der Entwickler kann auch eigene Tagsets entwickeln.  Es gibt eine Reihe empfohlener Tags \(siehe "Verwandte Abschnitte" in diesem Thema\).  Einige der empfohlenen Tags haben eine besondere Bedeutung:  
  
    -   Das \<param\>\-Tag wird zur Beschreibung von Parametern verwendet.  Bei Verwendung dieses Tags stellt der Compiler sicher, dass der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden.  Falls die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.  
  
    -   Das `cref`\-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen.  Der Compiler überprüft, ob dieses Codeelement vorhanden ist.  Falls die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.  Bei der Suche nach einem im `cref`\-Attribut beschriebenen Typ akzeptiert der Compiler auch die Verwendung von `Imports`\-Anweisungen.  
  
    -   Mithilfe des \<summary\>\-Tags werden von IntelliSense in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] zusätzliche Informationen über einen Typ oder einen Member angezeigt.  
  
## Verwandte Abschnitte  
 Weitere Informationen über das Erstellen einer XML\-Datei mit Dokumentationskommentaren finden Sie unter den folgenden Themen:  
  
-   [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Processing the XML File](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [XML\-Tools in Visual Studio](/visual-studio/xml-tools/xml-tools-in-visual-studio)  
  
## Siehe auch  
 [Entwickeln von Anwendungen mit Visual Basic](../../../visual-basic/developing-apps/index.md)   
 [Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md)
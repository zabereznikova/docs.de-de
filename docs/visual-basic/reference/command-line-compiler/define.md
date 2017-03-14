---
title: "/define (Visual Basic) | Microsoft Docs"
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
  - "-d compiler option [Visual Basic]"
  - "/d compiler option [Visual Basic]"
  - "-define compiler option [Visual Basic]"
  - "d compiler option [Visual Basic]"
  - "/define compiler option [Visual Basic]"
  - "define compiler option [Visual Basic]"
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /define (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Definiert Konstanten für die bedingte Kompilierung.  
  
## Syntax  
  
```  
/define:["]symbol[=value][,symbol[=value]]["] ' -or- /d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`symbol`|Erforderlich.  Das zu definierende Symbol.|  
|`value`|Dies ist optional.  Der Wert, der `symbol` zugewiesen werden soll.  Wenn `value` eine Zeichenfolge ist, muss es von einer Kombination aus umgekehrtem Schrägstrich\/Anführungszeichen \(\\"\) umgeben sein statt Anführungszeichen.  Wurde kein Wert festgelegt, dann wird er als True angenommen.|  
  
## Hinweise  
 Die Option `/define` hat einen ähnlichen Effekt wie das Verwenden einer `#Const`\-Präprozessordirektive in der Quelldatei, außer dass mit `/define` definierte Konstanten öffentlich sind und für alle Dateien im Projekt gelten.  
  
 Sie können Symbole, die mit dieser Option erstellt wurden, mit der `#If`...`Then`...`#Else`\-Direktive verwenden, um Quelldateien bedingt zu kompilieren.  
  
 `/d` ist die Kurzform von `/define`.  
  
 Sie können mehrere Symbole mit `/define` definieren, wenn Sie kommagetrennte Symboldefinitionen verwenden.  
  
||  
|-|  
|So definieren Sie die integrierte Visual Studio\-Entwicklungsumgebung|  
|1.  Ein Projekt auswählen in **Projektmappen\-Explorer**.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweitert**.<br />4.  Ändern Sie den Wert im Feld **Benutzerdefinierte Konstanten**.|  
  
## Beispiel  
 Der folgende Code definiert zwei konditionelle Compilerkonstanten und verwendet sie anschließend.  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
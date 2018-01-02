---
title: /define (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62669ec40803170cb623382b09472b82121d26bb
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="define-visual-basic"></a>/define (Visual Basic)
Definiert Konstanten für die bedingte Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`symbol`|Erforderlich. Das zu definierende Symbol.|  
|`value`|Dies ist optional. Der Wert, der `symbol` zugewiesen werden soll. Wenn `value` ist eine Zeichenfolge, muss Sie von Sequenzen von umgekehrtem Schrägstrich/Anführungszeichen eingeschlossen sein (\\") anstelle von Anführungszeichen. Wurde kein Wert festgelegt, dann wird er als True angenommen.|  
  
## <a name="remarks"></a>Hinweise  
 Die Option `/define` hat einen ähnlichen Effekt wie das Verwenden einer `#Const`-Präprozessordirektive in der Quelldatei, außer dass mit `/define` definierte Konstanten öffentlich sind und für alle Dateien im Projekt gelten.  
  
 Sie können Symbole, die mit dieser Option erstellt wurden, mit der `#If`...`Then`...`#Else`-Direktive verwenden, um Quelldateien bedingt zu kompilieren.  
  
 `/d`ist die Kurzform der `/define`.  
  
 Sie können mehrere Symbole mit `/define` definieren, wenn Sie kommagetrennte Symboldefinitionen verwenden.  
  
|So definieren Sie die integrierte Visual Studio-Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **erweiterte**.<br />4.  Ändern Sie den Wert in der **benutzerdefinierte Konstanten** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code definiert zwei konditionelle Compilerkonstanten und verwendet sie anschließend.  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: 5035466de4aa17c374824e1b0f02ed594731a9d3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716800"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
Definiert Konstanten für die bedingte Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

oder

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`symbol`|Erforderlich Das zu definierende Symbol.|  
|`value`|Dies ist optional. Der Wert, der `symbol` zugewiesen werden soll. Wenn `value` eine Zeichenfolge ist, muss Sie anstelle von Anführungszeichen von umgekehrten Schrägstrichen/Anführungszeichen Sequenzen (\\") umgeben sein. Wurde kein Wert festgelegt, dann wird er als True angenommen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-define`-Option ähnelt der Verwendung einer `#Const`-Präprozessordirektive in der Quelldatei, mit der Ausnahme, dass mit `-define` definierte Konstanten öffentlich sind und für alle Dateien im Projekt gelten.  
  
 Sie können Symbole, die mit dieser Option erstellt wurden, mit der `#If`...`Then`...`#Else`-Anweisung verwenden, um Quelldateien bedingt zu kompilieren.  
  
 `-d` ist die Kurzform `-define`.  
  
 Sie können mehrere Symbole mit `-define` definieren, wenn Sie kommagetrennte Symboldefinitionen verwenden.  
  
|So legen Sie-define in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|---|  
|1. Wählen Sie ein Projekt aus, das in **Projektmappen-Explorer**ausgewählt ist. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2. Klicken Sie auf die Registerkarte **Kompilieren** .<br />3. Klicken Sie auf **erweitert**.<br />4. ändern Sie den Wert im Feld **benutzerdefinierte Konstanten** .|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code definiert zwei konditionelle Compilerkonstanten und verwendet sie anschließend.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

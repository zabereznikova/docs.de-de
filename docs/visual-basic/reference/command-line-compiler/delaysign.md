---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 6d3c89d598714446e04ba40155951f771d474866
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971989"
---
# <a name="-delaysign"></a>-delaysign
Gibt an, ob die Assembly vollständig oder teilweise signiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll. Verwenden `-delaysign+` Sie, wenn Sie den öffentlichen Schlüssel in der Assembly platzieren und Speicherplatz für den signierten Hash reservieren möchten. Die Standardeinstellung ist `-delaysign-`.  
  
## <a name="remarks"></a>Hinweise  
 Die `-delaysign` -Option hat keine Auswirkung, wenn Sie nicht mit [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)verwendet wird.  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert. Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert. Wenn eine Assembly mit Verzögerung signiert wird, wird die Signatur vom Compiler nicht berechnet und gespeichert, sondern es wird ein Speicherplatz in der Datei reserviert, damit die Signatur später hinzugefügt werden kann.  
  
 Mithilfe `-delaysign+`von kann ein Entwickler in einer Organisation z. b. nicht signierte Testversionen einer Assembly verteilen, die Tester mit dem globalen Assemblycache registrieren und verwenden können. Wenn die Arbeit an der Assembly abgeschlossen ist, kann die Person, die für den privaten Schlüssel der Organisation zuständig ist, die Assembly vollständig signieren. Diese gliementalisierung schützt den privaten Schlüssel der Organisation vor der Offenlegung und ermöglicht allen Entwicklern, an den Assemblys zu arbeiten.  
  
 Weitere Informationen zum Signieren einer Assembly finden [Sie unter Erstellen und verwenden](../../../standard/assembly/create-use-strong-named.md) von Assemblys mit starkem Namen.  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>So legen Sie-Delta Sign in der integrierten Entwicklungsumgebung von Visual Studio fest  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2. Klicken Sie auf die Registerkarte **Signierung**.  
  
3. Legen Sie den Wert im Feld **Verzögertes Signieren** fest.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

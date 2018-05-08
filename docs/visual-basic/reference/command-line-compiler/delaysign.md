---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c979ada9984ef345ffbb6b5e29c2f30595c3074d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-delaysign"></a>-delaysign
Gibt an, ob die Assembly vollständig oder teilweise signiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll. Verwendung `-delaysign+` Wenn Sie den öffentlichen Schlüssel in der Assembly und reservierte Speicherplatz für den signierten Hash platzieren möchten. Die Standardeinstellung ist `-delaysign-`.  
  
## <a name="remarks"></a>Hinweise  
 Die `-delaysign` Option hat keine Auswirkung, wenn nicht mit [- Keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [- Keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert. Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert. Wenn eine Assembly verzögert signiert wird, wird der Compiler nicht berechnen und speichern die Signatur, sondern reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.  
  
 Z. B. durch Verwendung `-delaysign+`, ein Entwickler in einer Organisation kann verteilen, ohne Vorzeichen Testversionen einer Assembly, die Tester mit dem globalen Assemblycache zu registrieren und verwenden können. Bei der Arbeit für die Assembly abgeschlossen ist, kann für private Schlüssel der Organisation verantwortliche Person die Assembly vollständig signieren. Diese Aufgliederung schützt private Schlüssel der Organisation vor Offenlegung, während alle es Entwicklern ermöglicht, auf die Assemblys zu arbeiten.  
  
 Finden Sie unter [erstellen und Verwenden von Assemblys](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>-Delaysign in der integrierten Visual Studio-Entwicklungsumgebung fest  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2.  Klicken Sie auf die Registerkarte **Signierung**.  
  
3.  Legen Sie den Wert der **nur verzögerte Signierung** Feld.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

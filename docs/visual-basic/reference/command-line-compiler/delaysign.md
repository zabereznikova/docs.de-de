---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 1459484b858137836fcfdcd9db46d8e99a06e9c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185208"
---
# <a name="-delaysign"></a>-delaysign
Gibt an, ob die Assembly vollständig oder teilweise signiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll. Verwendung `-delaysign+` sollten Sie den öffentlichen Schlüssel in der Assembly und der reservierte Speicherplatz für den signierten Hash zu platzieren. Die Standardeinstellung ist `-delaysign-`.  
  
## <a name="remarks"></a>Hinweise  
 Die `-delaysign` Option hat keine Auswirkung, wenn Sie mit [- Keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [- Keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert. Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert. Wenn eine Assembly verzögert signiert wird, der Compiler nicht berechnet und speichern die Signatur aber reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.  
  
 Z. B. durch Verwendung `-delaysign+`, ein Entwickler in einer Organisation verteilen ohne Vorzeichen Testversionen einer Assembly, die Tester mit dem globalen Assemblycache zu registrieren und verwenden können. Wenn für die Assembly abgeschlossen ist, kann für private Schlüssel der Organisation verantwortliche Person die Assembly vollständig signiert. Diese Trennung schützt die privaten Schlüssel der Organisation vor Offenlegung, gleichzeitig alle Entwickler arbeiten, auf die Assemblys.  
  
 Finden Sie unter [erstellen und Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>-Delaysign in der integrierten Entwicklungsumgebung von Visual Studio festlegen.  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2.  Klicken Sie auf die Registerkarte **Signierung**.  
  
3.  Legen Sie den Wert der **nur verzögerte Signierung** Feld.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005401"
---
# <a name="-nowarn"></a>-nowarn
Unterdrückt die Compilerfunktion zum Generieren von Warnungen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`numberList`|Optional. Eine durch Trennzeichen getrennte Liste der Warnungs-ID-Nummern, die vom Compiler unterdrückt werden sollen. Wenn die Warnungs-IDs nicht angegeben werden, werden alle Warnungen unterdrückt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Option "`-nowarn`" bewirkt, dass der Compiler keine Warnungen generiert. Um eine einzelne Warnung zu unterdrücken, geben Sie die Warnungs-ID an die `-nowarn`-Option nach dem Doppelpunkt an. Trennen Sie mehrere Warnungs Nummern durch Kommas.  
  
 Sie müssen nur den numerischen Teil des Warnungs Bezeichners angeben. Wenn Sie z. b. BC42024 unterdrücken möchten, geben Sie die Warnung für nicht verwendete lokale Variablen an, `-nowarn:42024`.  
  
 Weitere Informationen zu den Warnungs-ID-Nummern finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|To Set-nowarn in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Aktivieren Sie das Kontrollkästchen **alle Warnungen deaktivieren** , um alle Warnungen zu deaktivieren.<br />     - oder -<br />     Um eine bestimmte Warnung zu deaktivieren, klicken Sie in der Dropdown Liste neben der Warnung auf **keine** .|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `T2.vb` und zeigt keine Warnungen an.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `T2.vb` und zeigt keine Warnungen für nicht verwendete lokale Variablen an (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)

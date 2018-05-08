---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 338b4672d215968275c30d37a2f8061e764aed8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-nowarn"></a>-nowarn
Unterdrückt die Compilerfunktion zum Generieren von Warnungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`numberList`|Dies ist optional. Durch Trennzeichen getrennte Liste von die Warnung-ID-Nummern, die der Compiler unterdrücken soll. Wenn die Warnung IDs nicht angegeben werden, werden alle Warnungen unterdrückt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-nowarn` Option bewirkt, dass der Compiler keine Warnungen generiert werden. Um eine einzelne Warnung zu unterdrücken, geben Sie die ID der Warnung, die die `-nowarn` Option nach dem Doppelpunkt ausmacht. Trennen Sie mehrere Warnungsnummern jeweils durch Kommas.  
  
 Sie müssen nur den numerischen Teil des Warnungsbezeichners angeben. Geben Sie z. B. wenn BC42024, das die Warnung für nicht verwendete lokale Variablen, unterdrückt werden sollen `-nowarn:42024`.  
  
 Weitere Informationen über die Warnung-ID-Nummern, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|-Nowarn in der integrierten Visual Studio-Entwicklungsumgebung fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Wählen Sie die **deaktivieren Sie alle Warnungen** Kontrollkästchen, um alle Warnungen zu deaktivieren.<br />     - oder -<br />     Um eine bestimmte Warnung zu deaktivieren, klicken Sie auf **keine** aus der Dropdownliste neben der Warnung.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und keine Warnungen angezeigt.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und die Warnungen für nicht verwendete lokale Variablen (42024) nicht angezeigt.  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)

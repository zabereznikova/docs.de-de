---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828211"
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
|`numberList`|Dies ist optional. Durch Trennzeichen getrennte Liste mit der ID-Warnzahlen, die der Compiler unterdrücken soll. Wenn keine Warnungs-IDs angegeben sind, werden alle Warnungen unterdrückt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-nowarn` Option bewirkt, dass den Compiler keine Warnungen generiert werden. Um eine einzelne Warnung zu unterdrücken, geben Sie die ID der Warnung, die die `-nowarn` Option, die hinter dem Doppelpunkt. Trennen Sie mehrere Warnungsnummern jeweils durch Kommas.  
  
 Sie müssen nur den numerischen Teil des Warnungsbezeichners angeben. Wenn Sie BC42024, die Warnung für nicht verwendete lokale Variablen, unterdrücken möchten, z. B. Geben Sie `-nowarn:42024`.  
  
 Weitere Informationen zu die Warnung-ID-Nummern, finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|-Nowarn in der integrierten Entwicklungsumgebung von Visual Studio festlegen.|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Wählen Sie die **alle Warnungen deaktivieren** Kontrollkästchen, um alle Warnungen deaktivieren.<br />     - oder -<br />     Um eine bestimmte Warnung zu deaktivieren, klicken Sie auf **keine** aus der Dropdown-Liste neben der Warnung.|  
  
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

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)

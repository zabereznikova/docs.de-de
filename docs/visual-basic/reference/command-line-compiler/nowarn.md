---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 37851f99eb88543e939ce48995ded41958e57cc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397487"
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
|`numberList`|Dies ist optional. Dies ist eine durch Trennzeichen getrennte Liste der Warnungs-ID-Nummern, die vom Compiler unterdrückt werden sollen. Wenn die Warnungs-IDs nicht angegeben werden, werden alle Warnungen unterdrückt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Option `-nowarn` bewirkt, dass der Compiler kein Warnungen generiert. Fügen Sie nach der Option `-nowarn` und einem darauf folgenden Doppelpunkt die Warnungs-ID ein, um eine einzelne Warnung zu unterdrücken. Trennen Sie mehrere Warnnummern durch ein Komma.  
  
 Sie müssen lediglich den numerischen Teil des Warnungsbezeichners angeben. Geben Sie `-nowarn:42024` an, wenn Sie z. B. BC42024 unterdrücken möchten (Warnung für nicht verwendete lokale Variablen).  
  
 Weitere Informationen zu Warnungs-IDs finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Festlegen von -nowarn in der integrierten Visual Studio-Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**, um alle Warnungen zu deaktivieren.<br />     - oder -<br />     Klicken Sie in der Dropdownliste neben der Warnung auf **Keine**, um eine bestimmte Warnung zu deaktivieren.|  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert, und es werden keine Warnungen angezeigt.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert, und es werden keine Warnungen für nicht verwendete lokale Variablen (42024) angezeigt.  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)

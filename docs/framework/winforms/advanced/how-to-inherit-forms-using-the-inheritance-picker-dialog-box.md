---
title: 'Vorgehensweise: Erben von Formularen mithilfe des Dialogfelds „Vererbungsauswahl“'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], forms
- Inheritance Picker dialog box
- inherited forms [Windows Forms], creating
ms.assetid: 969b4c04-12aa-4297-93a2-0ae747447823
ms.openlocfilehash: 5ae1c236835141b10bc704cd39f55de6e3e974b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342088"
---
# <a name="how-to-inherit-forms-using-the-inheritance-picker-dialog-box"></a>Vorgehensweise: Erben von Formularen mithilfe des Dialogfelds „Vererbungsauswahl“
Das Dialogfeld **Vererbungsauswahl** bietet die einfachste Möglichkeit, ein Formular oder ein anderes Objekt zu erben. Mithilfe dieser Option können Sie die Vorteile von Codezeichenfolgen oder Benutzeroberflächen (UI) nutzen, die Sie bereits in anderen Projektmappen erstellt haben.  
  
> [!NOTE]
>  Damit die Formularvererbung vom Dialogfeld **Vererbungsauswahl** unterstützt wird, muss das Projekt mit dem jeweiligen Formular in eine ausführbare Datei oder DLL integriert werden. Wählen Sie zum Erstellen des Projekts aus dem Menü **Erstellen** die Option **Projektmappe** aus.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-windows-form-inherited-from-an-existing-form-by-using-the-inheritance-picker"></a>So erstellen Sie ein von einem vorhandenen Formular geerbtes Windows Form mithilfe der Vererbungsauswahl  
  
1. Wählen Sie aus dem Menü **Projekt** die Option **Windows Form hinzufügen** aus.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2. Suchen der **geerbtes Formular** Vorlage entweder auf die Searchbox oder durch Klicken auf die **Windows Forms** Kategorie auszuwählen, und nennen Sie sie in der **Namen** Feld. Klicken Sie auf die Schaltfläche **Hinzufügen**, um fortzufahren.  
  
     Das Dialogfeld **Vererbungsauswahl** wird geöffnet. Wenn das aktuelle Projekt bereits Formulare enthält, werden diese im Dialogfeld **Vererbungsauswahl** angezeigt.  
  
3. Um von einem Formular in einer anderen Assembly zu erben, klicken Sie auf die Schaltfläche **Durchsuchen**.  
  
4. Navigieren Sie im Dialogfeld **Eine Datei auswählen, die eine Komponente für die Vererbung enthält** zu dem Projekt, das das gewünschte Formular oder Modul enthält.  
  
5. Klicken Sie auf den Namen der EXE- oder DLL-Datei, um sie auszuwählen, und klicken Sie dann auf die Schaltfläche **Öffnen**.  
  
     Daraufhin kehren Sie zum Dialogfeld **Vererbungsauswahl** zurück, in dem jetzt die Komponente zusammen mit dem Projekt, in dem sie gespeichert ist, aufgelistet wird.  
  
6. Wählen Sie die Komponente aus.  
  
     Die Komponente wird im **Projektmappen-Explorer** zu Ihrem Projekt hinzugefügt. Wenn sie eine Benutzeroberfläche verfügt, Steuerelemente, die Bestandteil des geerbten Formulars sind durch ein Symbol markiert (![Screenshot von der Visual Basic-Vererbung-Symbol.](./media/how-to-inherit-forms-using-the-inheritance-picker-dialog-box/visual-basic-inheritance-glyph.gif)), und bei Auswahl dieser Option müssen Sie einen Rahmen, der angibt, der Sicherheitsebene das Steuerelement besitzt, auf die Form der Komponente. In der folgenden Tabelle sind die Verhaltensweisen aufgeführt, die den verschiedenen Sicherheitsebenen entsprechen.  
  
    |Sicherheitsebene des Steuerelements|Mögliche Interaktion mit geerbtem Formular im Designer und Code-Editor|  
    |-------------------------------|--------------------------------------------------------------------------------|  
    |Public|Standardrahmen mit Ziehpunkten: Das Steuerelement kann vergrößert, verkleinert und verschoben werden. Auf das Steuerelement kann intern durch die Klasse, durch die es deklariert wird, und extern durch andere Klassen zugegriffen werden.|  
    |Protected|Standardrahmen mit Ziehpunkten: Das Steuerelement kann vergrößert, verkleinert und verschoben werden. Auf das Steuerelement kann intern durch die Klasse, durch die es deklariert wird, und durch alle Klassen, die von der übergeordneten Klasse erben, nicht jedoch durch externe Klassen zugegriffen werden.|  
    |Protected Internal (Protected Friend in Visual Basic)|Standardrahmen mit Ziehpunkten: Das Steuerelement kann vergrößert, verkleinert und verschoben werden. Auf das Steuerelement kann intern durch die Klasse, durch die es deklariert wird, durch alle Klassen, die von der übergeordneten Klasse erben, sowie durch andere Member der Assembly, die es enthält, zugegriffen werden.|  
    |Internal (Friend in Visual Basic)|Standardrahmen ohne Ziehpunkte: Das Steuerelement wird im Formular angezeigt, und seine Eigenschaften sind im Fenster **Eigenschaften** sichtbar. Sämtliche Merkmale des Steuerelements werden jedoch als schreibgeschützt betrachtet. Das Steuerelement kann nicht verschoben und Größe oder Eigenschaften können nicht geändert werden. Wenn es sich bei dem Steuerelement um einen Container für andere Steuerelemente (z. B. um ein Gruppenfeld) handelt, können keine neuen Steuerelemente hinzugefügt und keine vorhandenen Steuerelemente entfernt werden. Dies gilt auch dann, wenn diese Steuerelemente die "Public"-Eigenschaft besitzen. Auf das Steuerelement können nur andere Member der Assembly zugreifen, die es enthält.|  
    |Private|Standardrahmen ohne Ziehpunkte: Das Steuerelement wird im Formular angezeigt, und seine Eigenschaften sind im Fenster **Eigenschaften** sichtbar. Sämtliche Merkmale des Steuerelements werden jedoch als schreibgeschützt betrachtet. Das Steuerelement kann nicht verschoben und Größe oder Eigenschaften können nicht geändert werden. Wenn es sich bei dem Steuerelement um einen Container für andere Steuerelemente (z. B. um ein Gruppenfeld) handelt, können keine neuen Steuerelemente hinzugefügt und keine vorhandenen Steuerelemente entfernt werden. Dies gilt auch dann, wenn diese Steuerelemente die "Public"-Eigenschaft besitzen. Auf das Steuerelement kann nur durch die Klasse zugegriffen werden, durch die es deklariert wird.|  
  
     Informationen zum Ändern der Darstellung eines Basisformulars finden Sie unter [Auswirkungen beim Ändern der Darstellung von Basisformularen](effects-of-modifying-base-form-appearance.md).  
  
    > [!NOTE]
    >  Wenn Sie geerbte Steuerelemente und Komponenten mit standardmäßigen Steuerelementen und Komponenten in Windows Forms kombinieren, treten möglicherweise Konflikte hinsichtlich der Z-Reihenfolge auf. Sie können diese Probleme lösen, indem Sie die Z-Reihenfolge ändern. Zeigen Sie hierzu im Menü **Format** auf **Reihenfolge** und klicken Sie anschließend auf **In den Vordergrund** oder **In den Hintergrund**. Weitere Informationen zur Z-Reihenfolge von Steuerelementen finden Sie unter [Vorgehensweise: Überlagern von Objekten in Windows Forms](../controls/how-to-layer-objects-on-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch

- [Inherits-Anweisung](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [using](~/docs/csharp/language-reference/keywords/using.md)
- [Auswirkungen beim Ändern der Darstellung von Basisformularen](effects-of-modifying-base-form-appearance.md)
- [Visuelle Vererbung in Windows Forms](windows-forms-visual-inheritance.md)

---
title: 'Gewusst wie: Erstellen von zusammengesetzten Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 42ea424507b89576df8099fd4849dd2665135a55
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459436"
---
# <a name="how-to-author-composite-controls"></a>Gewusst wie: Erstellen von zusammengesetzten Steuerelementen

Zusammengesetzte Steuerelemente können auf viele Arten eingesetzt werden. Sie können sie als Teil eines Desktopanwendungsprojekts von Windows erstellen und nur für Formulare im Projekt verwenden. Oder Sie können sie in einem Windows-Steuerelementbibliothek-Projekt erstellen, das Projekt in eine Assembly kompilieren und die Steuerelemente in anderen Projekten verwenden. Sie können sogar von Ihnen erben und visuelle Vererbung verwenden, um Sie schnell für spezielle Zwecke anzupassen.

## <a name="to-author-a-composite-control"></a>So erstellen Sie ein zusammengesetztes Steuerelement

1. Erstellen Sie in Visual Studio ein neues **Windows-Anwendungs** Projekt, und nennen Sie es **DemoControlHost**.

2. Klicken Sie im Menü **Projekt** auf **Benutzersteuerelement hinzufügen**.

3. Geben Sie im Dialogfeld **Neues Element hinzufügen** der Klassendatei (VB- oder CS-Datei) den Namen, den das zusammengesetzte Steuerelement tragen soll.

4. Wählen Sie die Schaltfläche **Hinzufügen** , um die Klassendatei für das zusammengesetzte Steuerelement zu erstellen

5. Fügen Sie Steuerelemente aus der **Toolbox** zur Oberfläche des zusammengesetzten Steuerelements hinzu.

6. Platzieren Sie Code in Ereignisprozeduren, um Ereignisse zu behandeln, die vom zusammengesetzten Steuerelement oder konstituierenden Steuerelementen ausgelöst wurden.

7. Schließen Sie den Designer für das zusammengesetzte Steuerelement, und speichern Sie die Datei, wenn Sie dazu aufgefordert werden.

8. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

     Das Projekt muss erstellt werden, damit benutzerdefinierte Steuerelemente in der **Toolbox** angezeigt werden.

9. Verwenden Sie die Registerkarte **DemoControlHost** der **Toolbox**, um Instanzen Ihres Steuerelements zu `Form1` hinzuzufügen.

## <a name="to-author-a-control-class-library"></a>So erstellen Sie eine Steuerelementklassenbibliothek

1. Öffnen Sie ein neues **Windows-Steuerelementbibliothek**-Projekt.

     Standardmäßig enthält das Projekt ein zusammengesetztes Steuerelement.

2. Fügen Sie Steuerelemente und Code wie im beschriebenen Verfahren hinzu.

3. Wählen Sie ein Steuerelement aus, das von vererbenden Klassen nicht geändert werden soll, und legen Sie die Eigenschaft des **Modifizierers** auf **Privat** fest.

4. Erstellen Sie die DLL.

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a>So erben Sie in einer Steuerelementklassenbibliothek von einem zusammengesetzten Steuerelement

1. Zeigen Sie im Menü **Datei** mit der Maus auf **Hinzufügen**, und wählen Sie **Neues Projekt** aus, um ein neues **Windows-Anwendungs**-Projekt zur Projektmappe hinzuzufügen.

2. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner **Verweise** für das neue Projekt, und wählen Sie **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** zu öffnen.

3. Wählen Sie die Registerkarte **Projekte** aus, und doppelklicken Sie auf Ihr Steuerelementbibliotheksprojekt.

4. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

5. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Steuerelementbibliotheksprojekt, und wählen Sie dann **Neues Element hinzufügen** aus dem Kontextmenü aus.

6. Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement** aus dem Dialogfeld **Neues Element hinzufügen** aus.

7. Doppelklicken Sie im Dialogfeld **Vererbungsauswahl** auf das Steuerelement, von dem Sie erben möchten.

     Ein neues Steuerelement wird zu Ihrem Projekt hinzugefügt.

8. Öffnen Sie den visuellen Designer für das neue Steuerelement, und fügen Sie zusätzliche konstituierende Steuerelemente hinzu.

     Die konstituierenden Steuerelemente, die vom zusammengesetzten Steuerelement geerbt wurden, werden in Ihrer DLL angezeigt und Sie können die Eigenschaften von Steuerelementen ändern, deren Eigenschaft **Modifizierer** auf **Öffentlich** festgelegt ist. Sie können keine Eigenschaften von Steuerelementen ändern, deren Eigenschaft **Modifizierer** auf **Privat** festgelegt ist.

## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [Empfehlungen zum Typ von Steuerelementen](control-type-recommendations.md)
- [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Arten von benutzerdefinierten Steuerelementen](varieties-of-custom-controls.md)

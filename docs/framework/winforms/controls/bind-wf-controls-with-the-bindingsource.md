---
title: 'Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 180fafa9ace5927fd84ec5dc0a1b2a342f771efd
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040019"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers
Nachdem Sie dem Formular Steuerelemente hinzugefügt und die Benutzeroberfläche für die Anwendung bestimmt haben, können Sie die Steuerelemente an eine Datenquelle binden, sodass Benutzer zur Laufzeit Daten im Zusammenhang mit der Anwendung ändern und speichern können.

 Das Binden eines Steuer Elements oder einer Reihe von Steuerelementen in Windows Forms wird am <xref:System.Windows.Forms.BindingSource> einfachsten mit dem-Steuerelement als Brücke zwischen den Steuerelementen auf dem Formular und der Datenquelle erreicht.

 Mindestens ein Steuerelement in einem Formular kann an Daten gebunden werden. in der folgenden Prozedur ist ein <xref:System.Windows.Forms.TextBox> -Steuerelement an eine Datenquelle gebunden.

 Um das Verfahren abzuschließen, wird davon ausgegangen, dass Sie eine Bindung an eine Datenquelle herstellen, die von einer Datenbank abgeleitet ist. Weitere Informationen zum Erstellen von Datenquellen aus anderen Daten speichern finden Sie unter [Hinzufügen neuer Datenquellen](/visualstudio/data-tools/add-new-data-sources).

## <a name="to-bind-a-control-at-design-time"></a>So binden Sie ein Steuerelement zur Entwurfszeit

1. Ziehen Sie <xref:System.Windows.Forms.TextBox> ein-Steuerelement auf das Formular.

2. Im **Eigenschaften** Fenster:

    1. Erweitern Sie den Knoten **(DataBindings)** .

    2. Klicken Sie auf den Pfeil neben <xref:System.Windows.Forms.TextBox.Text%2A> der-Eigenschaft.

         Der Benutzeroberflächen-Typ-Editor für die **Daten** Quelle wird geöffnet.

         Wenn eine Datenquelle bereits für das Projekt oder Formular konfiguriert wurde, wird Sie angezeigt.

3. Klicken Sie auf **Projektdatenquelle hinzufügen**, um die Daten zu verbinden und die Datenquelle zu erzeugen.

4. Klicken Sie auf der Startseite des **Assistenten zum Konfigurieren von Datenquellen** auf **Weiter**.

5. Wählen Sie auf der Seite **Daten Quellentyp auswählen** die Option **Datenbank**aus.

6. Wählen Sie auf der Seite **Wählen Sie Ihre Datenverbindung** aus eine Datenverbindung aus der Liste der verfügbaren Verbindungen aus. Wenn die gewünschte Datenverbindung nicht verfügbar ist, wählen Sie **neue Verbindung** aus, um eine neue Datenverbindung zu erstellen.

7. Wählen Sie **Ja, Verbindung speichern,** um die Verbindungs Zeichenfolge in der Anwendungs Konfigurationsdatei zu speichern.

8. Wählen Sie die Datenbankobjekte, die in die Anwendung gebracht werden sollen. Wählen Sie in diesem Fall ein Feld in einer Tabelle aus, das Sie <xref:System.Windows.Forms.TextBox> anzeigen möchten.

9. Ersetzen Sie den Standardnamen des Datasets falls gewünscht.

10. Klicken Sie auf **Fertig stellen**.

11. Klicken Sie im **Eigenschaften** Fenster erneut auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A> -Eigenschaft. Wählen Sie im **DataSource** -Typ-Editor für die Benutzeroberfläche den Namen des Felds <xref:System.Windows.Forms.TextBox> aus, an das die gebunden werden soll.

     Der Editor für die Benutzeroberflächen Typen " **DataSource** " wird <xref:System.Windows.Forms.BindingSource> geschlossen, und das DataSet und der für diese Datenverbindung spezifische Tabellen Adapter werden dem Formular hinzugefügt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Neue Datenquelle hinzufügen](/visualstudio/data-tools/add-new-data-sources)
- [Datenquellen Fenster](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))

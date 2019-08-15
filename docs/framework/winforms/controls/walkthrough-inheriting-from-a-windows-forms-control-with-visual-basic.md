---
title: 'Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual Basic'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: 0891b64fdb26953ab90f3da931f04513ac9e8bcf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040217"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a>Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual Basic
Mit Visual Basic können Sie durch *Vererbung*leistungsstarke benutzerdefinierte Steuerelemente erstellen. Durch Vererbung können Sie Steuerelemente erstellen, die die gesamte Funktionalität der standardmäßigen Windows Forms-Steuerelemente, aber auch benutzerdefinierte Funktionen enthalten. In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches geerbtes Steuerelement mit dem Namen `ValueButton`. Diese Schaltfläche erbt Funktionen vom Standard Windows Forms <xref:System.Windows.Forms.Button> -Steuerelement und macht eine benutzerdefinierte Eigenschaft `ButtonValue`mit dem Namen verfügbar.

## <a name="creating-the-project"></a>Erstellen des Projekts
 Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>So erstellen Sie die „ValueButtonLib“-Steuerelementbibliothek und das „ValueButton“-Steuerelement

1. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.

2. Wählen Sie die Projektvorlage **Windows Forms-Steuerelement Bibliothek** aus der Liste der Visual Basic Projekte `ValueButtonLib` aus, und geben Sie im Feld **Name den Namen** ein.

     Der Projektname `ValueButtonLib` wird standardmäßig auch dem Stammnamespace zugewiesen. Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren. Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ValueButton` bereitstellen, können Sie Ihre `ValueButton`-Komponente mithilfe von `ValueButtonLib.ValueButton` überprüfen. Weitere Informationen finden Sie unter [Namespaces in Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).

3. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **UserControl1.vb**, und wählen Sie im Kontextmenü **Umbenennen** aus. Ändern Sie den Dateinamen in `ValueButton.vb`. Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement „UserControl1“ umbenannt werden sollen.

4. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.

5. Öffnen Sie den Knoten **ValueButton.vb**, um die vom Designer generierte Codedatei **ValueButton.Designer.vb** anzuzeigen. Öffnen Sie diese Datei im **Code-Editor**.

6. Suchen Sie `Class` die- `Partial Public Class ValueButton`Anweisung,, und ändern Sie den Typ, von dem dieses <xref:System.Windows.Forms.UserControl> Steuer <xref:System.Windows.Forms.Button>Element erbt, von in. Dadurch kann das geerbte Steuerelement sämtliche Funktionen des <xref:System.Windows.Forms.Button> Steuer Elements erben.

7. Suchen Sie `InitializeComponent` die-Methode, und entfernen Sie die <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> Zeile, die die Eigenschaft zuweist. Diese Eigenschaft ist im <xref:System.Windows.Forms.Button> Steuerelement nicht vorhanden.

8. Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.

     Beachten Sie, dass kein visueller Designer mehr verfügbar ist. Da das <xref:System.Windows.Forms.Button> Steuerelement seine eigene Zeichnung durchführt, können Sie seine Darstellung im Designer nicht ändern. Die visuelle Darstellung ist identisch mit der der Klasse, von der Sie erbt (d. h.) <xref:System.Windows.Forms.Button>, es sei denn, Sie wird im Code geändert.

> [!NOTE]
>  Sie können trotzdem Komponenten, die über keine Benutzeroberflächenelemente verfügen, zur Entwurfsoberfläche hinzufügen.

## <a name="adding-a-property-to-your-inherited-control"></a>Hinzufügen einer Eigenschaft zum geerbten Steuerelement
 Eine Verwendungsmöglichkeit von geerbten Windows Forms-Steuerelementen ist das Erstellen von Steuerelementen, die in Aussehen und Verhalten mit den standardmäßigen Windows Forms-Steuerelementen identisch sind, aber benutzerdefinierte Eigenschaften verfügbar machen. In diesem Abschnitt fügen Sie eine Eigenschaft namens `ButtonValue` zum Steuerelement hinzu.

### <a name="to-add-the-value-property"></a>So fügen Sie die Value-Eigenschaft hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **ValueButton.vb**, und klicken Sie im Kontextmenü auf **Code anzeigen**.

2. Suchen Sie die `Public Class ValueButton`-Anweisung. Geben Sie unmittelbar unter dieser Anwendung den folgenden Code ein:

    ```vb
    ' Creates the private variable that will store the value of your
    ' property.
    Private varValue as integer
    ' Declares the property.
    Property ButtonValue() as Integer
    ' Sets the method for retrieving the value of your property.
       Get
          Return varValue
       End Get
    ' Sets the method for setting the value of your property.
       Set(ByVal Value as Integer)
          varValue = Value
       End Set
    End Property
    ```

     Dieser Code legt die Methoden fest, mit denen die Eigenschaft `ButtonValue` gespeichert und abgerufen wird. Die `Get`-Anweisung legt den zurückgegebenen Wert auf den Wert fest, der in der privaten Variablen `varValue` gespeichert ist. Die `Set`-Anweisung legt den Wert der privaten Variablen mithilfe des Schlüsselworts `Value` fest.

3. Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.

## <a name="testing-your-control"></a>Testen des Steuerelements
 Steuerelemente sind keine eigenständigen Projekte. Sie müssen in einem Container gehostet werden. Sie müssen ein Testprojekt erstellen, in dem das Steuerelement getestet werden kann. Sie müssen das Steuerelement auch für das Testprojekt zugänglich machen, indem Sie es erstellen (Kompilieren). In diesem Abschnitt erstellen Sie das Steuerelement und testen es in einem Windows Form.

### <a name="to-build-your-control"></a>So erstellen Sie das Steuerelement

1. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

     Der Build sollte ohne Compilerfehler oder Warnungen erfolgreich sein.

### <a name="to-create-a-test-project"></a>So Erstellen Sie ein Testprojekt

1. Zeigen Sie im Menü **Datei** mit der Maus auf **Hinzufügen**, und klicken Sie dann auf **Neues Projekt**, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.

2. Wählen Sie den Knoten Visual Basic Projekte aus, und klicken Sie auf **Windows Forms Anwendung**.

3. Geben Sie im Feld **Name** `Test`ein.

4. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.

5. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für Ihr Testprojekt, und wählen Sie dann im Kontextmenü **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.

6. Klicken Sie auf die Registerkarte **Projekte**.

7. Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**. Ihr `ValueButtonLib`-Projekt wird unter **Projektname** aufgelistet. Doppelklicken Sie auf das Projekt, um den Verweis auf das Testprojekt hinzuzufügen.

8. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test,** , und wählen Sie dann **Erstellen** aus.

### <a name="to-add-your-control-to-the-form"></a>So fügen Sie dem Formular ein Steuerelement hinzu

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Form1.vb**, und wählen Sie im Kontextmenü **Designer anzeigen** aus.

2. Klicken Sie in der **Toolbox** auf **ValueButtonLib Components**. Doppelklicken Sie auf **ValueButton**.

     Ein **ValueButton** wird im Formular angezeigt.

3. Klicken Sie mit der rechten Maustaste auf **ValueButton**, und wählen Sie im Kontextmenü **Eigenschaften** aus.

4. Untersuchen Sie im Fenster **Eigenschaften** die Eigenschaften dieses Steuerelements. Beachten Sie, dass sie mit den Eigenschaften identisch sind, die von einer Standardschaltfläche verfügbar gemacht werden, außer es besteht eine zusätzliche Eigenschaft `ButtonValue`.

5. Legen Sie die `ButtonValue` -Eigenschaft auf `5`fest.

6. Doppelklicken Sie auf der Registerkarte **alle Windows Forms** der **Toolbox**auf **Bezeichnung** , um dem <xref:System.Windows.Forms.Label> Formular ein Steuerelement hinzuzufügen.

7. Verschieben Sie die Bezeichnung in die Mitte des Formulars.

8. Doppelklicken Sie auf `ValueButton1`.

     Der **Code-Editor** wird im Ereignis `ValueButton1_Click` geöffnet.

9. Geben Sie die folgende Codezeile ein.

    ```vb
    Label1.Text = CStr(ValueButton1.ButtonValue)
    ```

10. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test**, und wählen Sie im Kontextmenü **Als Startprojekt festlegen** aus.

11. Wählen Sie im Menü **Debuggen** die Option **Debugging starten**.

     `Form1` wird angezeigt.

12. Klicken Sie auf `Valuebutton1`.

     Die Zahl '5' wird in `Label1` angezeigt und zeigt, dass die Eigenschaft `ButtonValue` Ihres geerbten Steuerelements mit der Methode `ValueButton1_Click` an `Label1` weitergegeben wurde. Daher erbt Ihr `ValueButton`-Steuerelement die gesamte Funktionalität der standardmäßigen Windows Forms-Schaltfläche und macht eine zusätzliche benutzerdefinierte Eigenschaft verfügbar.

## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Vorgehensweise: Anzeigen eines Steuer Elements im Dialog Feld "Toolbox Elemente auswählen"](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Grundlagen der Vererbung (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

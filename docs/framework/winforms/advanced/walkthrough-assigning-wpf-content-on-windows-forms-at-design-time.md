---
title: 'Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bc5f5e2d8808c0a60df721bf2c0ed76b45ef49a0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666262"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a>Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt zu Windows Forms zur Entwurfszeit

In diesem Artikel wird gezeigt, wie Sie die Windows Presentation Foundation (WPF)-Steuerelement Typen auswählen, die auf dem Formular angezeigt werden sollen. Sie können alle WPF-Steuerelementtypen auswählen, die im Projekt enthalten sind.

## <a name="prerequisites"></a>Vorraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt C# in `SelectingWpfContent`Visual Basic oder Visual mit dem Namen.

> [!NOTE]
> Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.

## <a name="create-the-wpf-control-types"></a>Erstellen der WPF-Steuerelement Typen

Nachdem Sie dem Projekt WPF-Steuerelementtypen hinzugefügt haben, können Sie diese in verschiedenen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelementen hosten.

1. Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu. Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)Entwurfszeit.

2. Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.

3. Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.FrameworkElement.Width%2A> der-Eigenschaft und der- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 200 fest.

4. Fügen Sie <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> ein <xref:System.Windows.Controls.UserControl> -Steuerelement hinzu, und <xref:System.Windows.Controls.TextBox.Text%2A> legen Sie den Wert der-Eigenschaft auf **gehosteten Inhalt**fest.

5. Fügen Sie dem Projekt ein zweites WPF-<xref:System.Windows.Controls.UserControl> hinzu. Verwenden Sie den Standardnamen, `UserControl2.xaml`, für den Steuerelementtyp.

6. Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.FrameworkElement.Width%2A> der-Eigenschaft und der- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 200 fest.

7. Fügen Sie <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> ein <xref:System.Windows.Controls.UserControl> -Steuerelement hinzu, und <xref:System.Windows.Controls.TextBox.Text%2A> legen Sie den Wert der-Eigenschaft auf **Hosted Content 2**fest.

   > [!NOTE]
   > Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.

8. Erstellen Sie das Projekt.

## <a name="select-wpf-controls"></a>WPF-Steuerelemente auswählen

Sie können einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement, das bereits Inhalte hostet, verschiedene WPF-Inhalte zuweisen.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

2. DoppelklickenSie `UserControl1` in der Toolbox auf, um eine Instanz von `UserControl1` auf dem Formular zu erstellen.

   Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.

3. Öffnen Sie im smarttagpanel für `elementHost1`die Dropdown Liste **gehostete Inhalte auswählen** .

4. Wählen Sie **UserControl2** aus dem Dropdown-Listenfeld aus.

   Das `elementHost1`-Steuerelement hostet jetzt eine Instanz des `UserControl2`-Typs.

5. Vergewissern Sie sich im Fenster **Eigenschaften** , dass <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> die-Eigenschaft auf **UserControl2**festgelegt ist.

6. Ziehen Sie ein <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement aus der **Toolbox**in der **WPF-Interoperabilitäts** Gruppe auf das Formular.

   Der Standardname für das neue Steuerelement ist `elementHost2`.

7. Öffnen Sie im smarttagpanel für `elementHost2`die Dropdown Liste **gehostete Inhalte auswählen** .

8. Wählen Sie in der Dropdown Liste **UserControl1** aus.

9. Das `elementHost2`-Steuerelement hostet jetzt eine Instanz des `UserControl1`-Typs.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)

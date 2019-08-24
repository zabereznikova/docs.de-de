---
title: 'Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft'
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: daf0c6495b89033e75c27a1ff0cbceaff9d85f34
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987161"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>Exemplarische Vorgehensweise: Layout von Steuerelementen mit Auffüll Zeichen, Rändern und der AutoSize-Eigenschaft

Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert. Das **Windows Forms-Designer** in Visual Studio bietet Ihnen viele Layouttools, die Sie erreichen können. Drei der wichtigsten sind die <xref:System.Windows.Forms.Control.Margin%2A>Eigenschaften, <xref:System.Windows.Forms.Control.Padding%2A>und, die <xref:System.Windows.Forms.Control.AutoSize%2A> für alle Windows Forms-Steuerelemente vorhanden sind.

Die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft definiert den Bereich um das Steuerelement, durch den andere Steuerelemente einen bestimmten Abstand von den Rändern des Steuerelements einhalten müssen.

Die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft definiert den Bereich innerhalb eines Steuerelements, durch den der Inhalt des Steuerelements (z. B. der Wert seiner <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft) einen bestimmten Abstand von den Rändern des Steuerelements einhalten muss.

Die folgende Abbildung zeigt die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft für ein Steuerelement.

![Ränder und Abstände bei Windows Forms-Steuerelementen](./media/vs-winformpadmargin.gif)

Die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft weist ein Steuerelement an, sich automatisch an seinen Inhalt zu anpassen. Die Größe wird nicht so geändert, dass Sie kleiner als der Wert der ursprünglichen <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft ist, und der Wert <xref:System.Windows.Forms.Control.Padding%2A> der zugehörigen-Eigenschaft wird berücksichtigt.

## <a name="prerequisites"></a>Vorraussetzungen

Sie benötigen Visual Studio, um diese exemplarische Vorgehensweise abzuschließen.

## <a name="create-the-project"></a>Erstellen eines Projekts

1. Erstellen Sie in Visual Studio ein **Windows-Anwendungs** Projekt `LayoutExample`mit dem Namen.

2. Wählen Sie in der **Windows Forms-Designer**das Formular aus.

## <a name="set-margins-for-controls"></a>Ränder für Steuerelemente festlegen

Sie können den Standardabstand zwischen den Steuerelementen mithilfe der <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft festlegen. Wenn Sie ein Steuerelement nahe genug auf ein anderes Steuerelement verschieben, wird eine Ausrichtungslinie angezeigt, in der die Ränder für die beiden Steuerelemente angezeigt werden. Das Steuerelement, das Sie verschieben, wird auch an den durch die Ränder definierten Abstand ausgerichtet.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Anordnen von Steuerelementen auf dem Formular mithilfe der Margin-Eigenschaft

1. Ziehen Sie <xref:System.Windows.Forms.Button> zwei-Steuerelemente aus der **Toolbox** auf das Formular.

2. Wählen Sie eines der <xref:System.Windows.Forms.Button> Steuerelemente aus, und verschieben Sie es in die Nähe der anderen, bis Sie fast berührt werden.

   Sehen Sie sich die angezeigte schräschlange an. Diese Distanz ist die Summe der <xref:System.Windows.Forms.Control.Margin%2A> Werte der beiden Steuerelemente. Das Steuerelement, das Sie in diese Entfernung verschieben. Weitere Informationen finden [Sie unter Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)von Richtungslinien.

3. Ändern Sie <xref:System.Windows.Forms.Control.Margin%2A> die-Eigenschaft eines der Steuerelemente, indem <xref:System.Windows.Forms.Control.Margin%2A> Sie den Eintrag im **Eigenschaften** Fenster erweitern und <xref:System.Windows.Forms.Padding.All%2A> die-Eigenschaft auf **20**festlegen.

4. Wählen Sie eines der <xref:System.Windows.Forms.Button> Steuerelemente aus, und verschieben Sie es in die Nähe des anderen.

   Die Richtungslinie, die die Summe der Randwerte definiert, ist länger, und das Steuerelement geht in einen größeren Abstand vom anderen Steuerelement.

5. Ändern Sie <xref:System.Windows.Forms.Control.Margin%2A> die-Eigenschaft des ausgewählten Steuer Elements, <xref:System.Windows.Forms.Control.Margin%2A> indem Sie im **Eigenschaften** Fenster den Eintrag erweitern <xref:System.Windows.Forms.Padding.Top%2A> und die-Eigenschaft auf **5**festlegen.

6. Verschieben Sie das ausgewählte Steuerelement unterhalb des anderen Steuer Elements, und beobachten Sie, dass die Ausrichtungslinie kürzer ist. Verschieben Sie das ausgewählte Steuerelement auf die linke Seite des anderen Steuer Elements, und beobachten Sie, dass die Ausrichtungslinie den in Schritt 4 beobachteten Wert beibehält.

7. Sie können jeden der Aspekte <xref:System.Windows.Forms.Control.Margin%2A> der-Eigenschaft <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A> <xref:System.Windows.Forms.Padding.Left%2A> <xref:System.Windows.Forms.Padding.Right%2A>,,, auf unterschiedliche <xref:System.Windows.Forms.Padding.All%2A> Werte festlegen, oder Sie können alle mit der-Eigenschaft auf denselben Wert festlegen.

## <a name="set-padding-for-controls"></a>Auffüllen für Steuerelemente festlegen

Um das genaue Layout zu erzielen, das für Ihre Anwendung erforderlich ist, enthalten die Steuerelemente häufig untergeordnete Steuerelemente. Verwenden Sie die- <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft des übergeordneten Steuer Elements in Verbindung mit der- <xref:System.Windows.Forms.Control.Margin%2A> Eigenschaft des untergeordneten Steuer Elements, wenn Sie die Nähe des Rahmens des untergeordneten Steuer Elements zum Rahmen des übergeordneten Steuer Elements angeben möchten. Die <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft wird auch zum Steuern der Nähe des Inhalts eines Steuer Elements (z. b. <xref:System.Windows.Forms.Button> die- <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft eines Steuer Elements) zu seinen Rahmen verwendet.

### <a name="arrange-controls-on-your-form-using-padding"></a>Anordnen von Steuerelementen auf dem Formular mithilfe von Auffüllung

1. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.

2. Ändern Sie den Wert der <xref:System.Windows.Forms.Button> -Eigenschaft <xref:System.Windows.Forms.Control.AutoSize%2A> des-Steuer Elements in **true**.

3. <xref:System.Windows.Forms.Padding.All%2A> <xref:System.Windows.Forms.Control.Padding%2A>Ändern Sie die- Eigenschaft,indemSieimEigenschaftenFensterdenEintragerweiternunddie-Eigenschaftauf5festlegen.<xref:System.Windows.Forms.Control.Padding%2A>

   Das-Steuerelement wird erweitert, um Platz für den neuen Leerraum bereitzustellen.

4. Ziehen Sie ein <xref:System.Windows.Forms.GroupBox> -Steuerelement aus der **Toolbox** auf das Formular. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der <xref:System.Windows.Forms.GroupBox> **Toolbox** in das-Steuerelement. Positionieren Sie <xref:System.Windows.Forms.Button> das Steuerelement so, dass es mit der unteren rechten Ecke <xref:System.Windows.Forms.GroupBox> des Steuer Elements geleert wird.

   Beachten Sie die Richtungslinien, die angezeigt werden <xref:System.Windows.Forms.Button> , wenn das-Steuerelement den unteren und <xref:System.Windows.Forms.GroupBox> rechten Rand des Steuer Elements nähert. Diese Richtungslinien entsprechen der <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft <xref:System.Windows.Forms.Button>von.

5. Ändern Sie <xref:System.Windows.Forms.GroupBox> die-Eigenschaft des-Steuer <xref:System.Windows.Forms.Control.Padding%2A> Elements, indem Sie den Eintrag im **Eigenschaften** Fenster erweitern und die <xref:System.Windows.Forms.Padding.All%2A> - <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft auf **20**festlegen.

6. Wählen Sie <xref:System.Windows.Forms.Button> das Steuerelement <xref:System.Windows.Forms.GroupBox> im-Steuerelement aus, und verschieben Sie <xref:System.Windows.Forms.GroupBox>es in die Mitte des.

   Die Richtungslinien werden in einer größeren Entfernung von den Rahmen des <xref:System.Windows.Forms.GroupBox> Steuer Elements angezeigt. Diese Distanz ist <xref:System.Windows.Forms.Button> die Summe aus der-Eigenschaft des- <xref:System.Windows.Forms.Control.Margin%2A> Steuer Elements und <xref:System.Windows.Forms.Control.Padding%2A> der-Eigenschaft des <xref:System.Windows.Forms.GroupBox> -Steuer Elements.

## <a name="size-controls-automatically"></a>Größe von Steuerelementen automatisch

Bei manchen Anwendungen ist die Größe eines-Steuer Elements zur Laufzeit nicht identisch wie zur Entwurfszeit. Der Text eines <xref:System.Windows.Forms.Button> Steuer Elements kann z. b. aus einer Datenbank entnommen werden, und seine Länge ist im Voraus nicht bekannt.

Wenn die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft auf `true`festgelegt ist, wird die Größe des Steuer Elements auf seinen Inhalt festgelegt. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md).

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>Anordnen von Steuerelementen auf dem Formular mithilfe der AutoSize-Eigenschaft

1. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular.

2. Ändern Sie den Wert der <xref:System.Windows.Forms.Button> -Eigenschaft <xref:System.Windows.Forms.Control.AutoSize%2A> des-Steuer Elements in **true**.

3. Ändern Sie <xref:System.Windows.Forms.Button> die- <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des Steuer Elements in **diese Schaltfläche hat eine lange Zeichenfolge für die Text-Eigenschaft**.

   Wenn Sie die Änderung übertragen, <xref:System.Windows.Forms.Button> ändert sich das Steuerelement selbst an den neuen Text.

4. Ziehen Sie <xref:System.Windows.Forms.Button> ein anderes Steuerelement aus der **Toolbox** auf das Formular.

5. Ändern Sie <xref:System.Windows.Forms.Button> die- <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des-Steuer Elements in "**diese Schaltfläche weist eine lange Zeichenfolge für die Text-Eigenschaft auf.** "

   Wenn Sie die Änderung übertragen, <xref:System.Windows.Forms.Button> ändert sich das Steuerelement nicht selbst, und der Text wird durch den rechten Rand des Steuer Elements abgeschnitten.

6. <xref:System.Windows.Forms.Padding.All%2A> <xref:System.Windows.Forms.Control.Padding%2A>Ändern Sie die- Eigenschaft,indemSieimEigenschaftenFensterdenEintragerweiternunddie-Eigenschaftauf5festlegen.<xref:System.Windows.Forms.Control.Padding%2A>

   Der Text im Inneren des Steuer Elements wird auf allen vier Seiten abgeschnitten.

7. Ändern Sie <xref:System.Windows.Forms.Button> die- <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft des-Steuer Elements in **true**.

   Die <xref:System.Windows.Forms.Button> Größe des Steuer Elements ändert sich in die gesamte Zeichenfolge. Außerdem wurde der Text Auffüllung um den Text erweitert, wodurch das <xref:System.Windows.Forms.Button> Steuerelement in alle vier Richtungen erweitert wird.

8. Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular. Positionieren Sie es in der Nähe der unteren rechten Ecke des Formulars.

9. Ändern Sie den Wert der <xref:System.Windows.Forms.Button> -Eigenschaft <xref:System.Windows.Forms.Control.AutoSize%2A> des-Steuer Elements in **true**.

10. Legen Sie <xref:System.Windows.Forms.Button> die- <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft des <xref:System.Windows.Forms.AnchorStyles.Right>- <xref:System.Windows.Forms.AnchorStyles.Bottom>Steuer Elements auf fest.

11. Ändern Sie <xref:System.Windows.Forms.Button> die- <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des-Steuer Elements in "**diese Schaltfläche weist eine lange Zeichenfolge für die Text-Eigenschaft auf.** "

   Wenn Sie einen Commit für die Änderung <xref:System.Windows.Forms.Button> durchsetzen, ändert sich das Steuerelement in sich nach links. Im allgemeinen erhöht die automatische Größenanpassung die Größe eines Steuer Elements in der Richtung, die <xref:System.Windows.Forms.Control.Anchor%2A> der Eigenschafts Einstellung entgegensteht.

## <a name="autosize-and-autosizemode-properties"></a>AutoSize-Eigenschaft und AutoSizeMode-Eigenschaft

 Einige Steuerelemente unter `AutoSizeMode` stützen die-Eigenschaft, die eine präzisere Steuerung des automatischen Größen Anpassungs Verhaltens eines Steuer Elements ermöglicht.

### <a name="use-the-autosizemode-property"></a>Verwenden der AutoSizeMode-Eigenschaft

1. Ziehen Sie ein <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Toolbox** auf das Formular.

2. Legen Sie den Wert der <xref:System.Windows.Forms.Panel> -Eigenschaft <xref:System.Windows.Forms.Control.AutoSize%2A> des-Steuer Elements auf **true**fest.

3. Ziehen Sie <xref:System.Windows.Forms.Button> ein-Steuerelement aus der <xref:System.Windows.Forms.Panel> **Toolbox** in das-Steuerelement.

4. Platzieren Sie <xref:System.Windows.Forms.Button> das Steuerelement in der Nähe der unteren rechten <xref:System.Windows.Forms.Panel> Ecke des-Steuer Elements.

5. Wählen Sie <xref:System.Windows.Forms.Panel> das Steuerelement aus, und ziehen Sie den unteren rechten Ziehpunkt. Ändern Sie die <xref:System.Windows.Forms.Panel> Größe des Steuer Elements, sodass es größer und kleiner ist.

   > [!NOTE]
   > Sie können die Größe des <xref:System.Windows.Forms.Panel> Steuer Elements frei ändern, aber Sie können es nicht kleiner als die Position <xref:System.Windows.Forms.Button> der unteren rechten Ecke des Steuer Elements anpassen. Dieses Verhalten wird durch den Standardwert `AutoSizeMode` der-Eigenschaft angegeben, <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>d. h.

6. Legen Sie den Wert der <xref:System.Windows.Forms.Panel> -Eigenschaft `AutoSizeMode` des- <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>Steuer Elements auf fest.

   Die <xref:System.Windows.Forms.Panel> Größe des Steuer Elements, um <xref:System.Windows.Forms.Button> das Steuerelement zu umschließen. Die Größe des <xref:System.Windows.Forms.Panel> Steuer Elements kann nicht geändert werden.

7. Ziehen Sie <xref:System.Windows.Forms.Button> das-Steuerelement in die obere linke Ecke <xref:System.Windows.Forms.Panel> des-Steuer Elements.

   Das <xref:System.Windows.Forms.Panel> -Steuerelement wird an <xref:System.Windows.Forms.Button> die neue Position des-Steuer Elements angepasst.

## <a name="next-steps"></a>Nächste Schritte

Es gibt noch viele weitere Layoutfeatures zum Anordnen von Steuerelementen in Ihren Windows Forms Anwendungen. Hier sind einige Kombinationen, die Sie möglicherweise ausprobieren:

- Erstellen Sie ein Formular mithilfe <xref:System.Windows.Forms.TableLayoutPanel> eines-Steuer Elements. Weitere Informationen finden [Sie unter Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Versuchen Sie, die Werte der <xref:System.Windows.Forms.TableLayoutPanel> -Eigenschaft <xref:System.Windows.Forms.Control.Padding%2A> des-Steuer Elements sowie die <xref:System.Windows.Forms.Control.Margin%2A> -Eigenschaft für die untergeordneten Steuerelemente zu ändern.

- Verwenden Sie das gleiche Experiment mit <xref:System.Windows.Forms.FlowLayoutPanel> einem-Steuerelement. Weitere Informationen finden [Sie unter Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe eines FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)-Elements.

- Experimentieren Sie mit dem Andocken <xref:System.Windows.Forms.Panel> von untergeordneten Steuerelementen in einem Die <xref:System.Windows.Forms.Control.Padding%2A> -Eigenschaft ist eine allgemeinere Umsetzung <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> der-Eigenschaft, und Sie können sich selbst darauf einstellen, dass dies der Fall ist, indem Sie <xref:System.Windows.Forms.Panel> ein untergeordnetes Steuerelement in ein <xref:System.Windows.Forms.Control.Dock%2A> -Steuerelement einfügen und die-Eigenschaft des untergeordneten Steuer Elements auf <xref:System.Windows.Forms.DockStyle.Fill>. Legen Sie <xref:System.Windows.Forms.Panel> die- <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft des Steuer Elements auf verschiedene Werte fest, und notieren Sie den Effekt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von Richtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)

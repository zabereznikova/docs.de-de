---
title: Hosten eines WPF-Verbundsteuerelements in Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: 88efab8adf36989938ba5aa887a28b41eb8820f3
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291624"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie jedoch über umfangreiche Investitionen in Windows Forms-Code verfügen, kann es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] effektiver sein, Ihre vorhandene Windows Forms-Anwendung mit zu erweitern, anstatt sie von Grund auf neu zu schreiben. Ein häufiges Szenario ist, wenn Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oder mehrere Steuerelemente einbetten möchten, die in Ihre Windows Forms-Anwendung implementiert sind. Weitere Informationen zum Anpassen von WPF-Steuerelementen finden Sie unter [Steuerelementanpassung](../controls/control-customization.md).  
  
 In dieser exemplarischen Vorgehensweise durchlaufen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Sie eine Anwendung, die ein zusammengesetztes Steuerelement hostet, um die Dateneingabe in einer Windows Forms-Anwendung auszuführen. Das zusammengesetzte Steuerelement ist in eine DLL verpackt. Dieses allgemeine Verfahren kann für komplexere Anwendungen und Steuerelemente erweitert werden. Diese exemplarische Vorgehensweise ist in Der Darstellung und Funktionalität nahezu identisch mit [der exemplarischen Vorgehensweise: Hosten eines Windows Forms Composite-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md). Der Hauptunterschied besteht darin, dass das Hosting-Szenario umgekehrt ist.  
  
 Diese exemplarische Vorgehensweise ist in zwei Abschnitte unterteilt. Im ersten Abschnitt wird kurz [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Implementierung des zusammengesetzten Steuerelements beschrieben. Im zweiten Abschnitt wird ausführlich erläutert, wie das zusammengesetzte Steuerelement in einer Windows Forms-Anwendung hosten, Ereignisse vom Steuerelement empfangen und auf einige Eigenschaften des Steuerelements zugreifen können.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
- Implementieren des zusammengesetzten WPF-Steuerelements  
  
- Implementieren der Windows Forms-Hostanwendung  
  
 Eine vollständige Codeliste der in dieser exemplarischen Vorgehensweise dargestellten Aufgaben finden Sie unter [Hosten eines WPF Composite Control in Windows Forms Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl).  
  
## <a name="prerequisites"></a>Voraussetzungen  

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementieren des zusammengesetzten WPF-Steuerelements  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in diesem Beispiel verwendete zusammengesetzte Steuerelement ist ein einfaches Dateneingabeformular, das den Namen und die Adresse des Benutzers annimmt. Klickt der Benutzer eine der zwei Schaltflächen, um anzugeben, dass die Aufgabe abgeschlossen ist, löst das Steuerelement ein benutzerdefiniertes Ereignis aus, um diese Informationen an den Host zurückzugeben. Die folgende Abbildung zeigt das gerenderte Steuerelement.

 Die folgende Abbildung zeigt ein WPF-Verbundsteuerelement:

 ![Screenshot, der ein einfaches WPF-Steuerelement zeigt.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1. Starten Sie Visual Studio, und öffnen Sie das Dialogfeld **Neues Projekt.**  
  
2. Wählen Sie in Visual C- und der Windows-Kategorie die **Vorlage WPF-Benutzersteuerungsbibliothek** aus.  
  
3. Geben Sie dem neuen Projekt den Namen `MyControls`.  
  
4. Geben Sie für den Speicherort einen bequem benannten `WindowsFormsHostingWpfControl`Ordner der obersten Ebene an, z. B. . Sie werden die Host-Anwendung später in diesem Ordner ablegen.  
  
5. Klicken Sie auf **OK**, um das Projekt zu erstellen. Das Standardprojekt enthält ein `UserControl1`einzelnes Steuerelement mit dem Namen .  
  
6. Benennen `UserControl1` Sie im Projektmappen-Explorer in um. `MyControl1`  
  
 Das Projekt sollte Verweise auf die folgenden System-DLLs aufweisen. Sollten eine oder mehrere dieser DLLs nicht standardmäßig enthalten sein, fügen Sie diese manuell zum Projekt hinzu.  
  
- PresentationCore  
  
- PresentationFramework  
  
- System  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Erstellen der Benutzeroberfläche  
 Die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für die Zusammengesetzte [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Steuerung wird mit implementiert. Das zusammengesetzte [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelement <xref:System.Windows.Controls.TextBox> besteht aus fünf Elementen. Jedem <xref:System.Windows.Controls.TextBox> Element ist <xref:System.Windows.Controls.TextBlock> ein Element zugeordnet, das als Bezeichnung dient. Unten befinden <xref:System.Windows.Controls.Button> sich zwei Elemente: **OK** und **Abbrechen**. Wenn der Benutzer auf eine Schaltfläche klickt, löst das Steuerelement ein benutzerdefiniertes Ereignis aus, um die Informationen an den Host zurückzugeben.  
  
#### <a name="basic-layout"></a>Grundlegendes Layout  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] verschiedenen Elemente sind <xref:System.Windows.Controls.Grid> in einem Element enthalten. Sie können <xref:System.Windows.Controls.Grid> den Inhalt des zusammengesetzten Steuerelements ähnlich anordnen, wie Sie ein `Table` Element in HTML verwenden würden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hat auch <xref:System.Windows.Documents.Table> ein <xref:System.Windows.Controls.Grid> Element, ist aber leichter und besser geeignet für einfache Layout-Aufgaben.  
  
 Das grundlegende Layout ist im nachfolgenden XAML-Code beschrieben. Dieser XAML definiert die Gesamtstruktur des Steuerelements, indem die <xref:System.Windows.Controls.Grid> Anzahl der Spalten und Zeilen im Element angegeben wird.  
  
 Ersetzen Sie in MyControl1.xaml den vorhandenen XAML-Code durch den folgenden.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>TextBlock- und TextBox-Elemente zum Raster hinzufügen  
 Sie platzieren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ein Element im Raster, <xref:System.Windows.Controls.Grid.RowProperty> indem <xref:System.Windows.Controls.Grid.ColumnProperty> Sie die Elementelemente und Attribute auf die entsprechende Zeilen- und Spaltennummer festlegen. Denken Sie daran, dass die Nummerierungen der Zeilen und Spalten nullbasiert sind. Sie können festlegen, dass ein <xref:System.Windows.Controls.Grid.ColumnSpanProperty> Element mehrere Spalten umfasst, indem Sie sein Attribut festlegen. Weitere Informationen <xref:System.Windows.Controls.Grid> zu Elementen finden Sie unter [Erstellen eines Rasterelements](../controls/how-to-create-a-grid-element.md).  
  
 Das folgende XAML zeigt die <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBlock> zusammengesetzten <xref:System.Windows.Controls.Grid.RowProperty> Steuerelemente und Elemente mit ihren und <xref:System.Windows.Controls.Grid.ColumnProperty> Attributen, die so eingestellt sind, dass die Elemente ordnungsgemäß im Raster platziert werden.  
  
 Fügen Sie in MyControl1.xaml das folgende <xref:System.Windows.Controls.Grid> XAML innerhalb des Elements hinzu.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Formatieren der Benutzeroberflächenelemente  
 Viele der Elemente auf dem Dateneingabeformular verfügen über ein ähnliches Erscheinungsbild, was bedeutet, dass viele ihrer Eigenschaften identische Einstellungen aufweisen. Anstatt die Attribute jedes Elements separat festzulegen, verwendet <xref:System.Windows.Style> das vorherige XAML Elemente, um Standardeigenschafteneinstellungen für Elementklassen zu definieren. Dieser Ansatz reduziert die Komplexität des Steuerelements und ermöglicht es Ihnen, die Darstellung mehrerer Elemente durch ein einziges Stilattribut zu ändern.  
  
 Die <xref:System.Windows.Style> Elemente sind <xref:System.Windows.Controls.Grid> in der <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft des Elements enthalten, sodass sie von allen Elementen im Steuerelement verwendet werden können. Wenn ein Stil benannt ist, wenden Sie <xref:System.Windows.Style> ihn auf ein Element an, indem Sie dem Namen des Stils ein Element hinzufügen, das festgelegt ist. Unbenannte Stile werden zum Standardstil für das Element. Weitere Informationen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu Stilen finden Sie unter [Styling und Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
 Das folgende XAML <xref:System.Windows.Style> zeigt die Elemente für das zusammengesetzte Steuerelement. Wie die Stile auf Elemente angewendet werden, können Sie dem vorherigen XAML-Code entnehmen. Beispielsweise hat das <xref:System.Windows.Controls.TextBlock> letzte `inlineText` Element den Stil, und das letzte <xref:System.Windows.Controls.TextBox> Element verwendet den Standardstil.  
  
 Fügen Sie in MyControl1.xaml das folgende <xref:System.Windows.Controls.Grid> XAML direkt nach dem Startelement hinzu.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Hinzufügen der Schaltflächen „OK” und „Abbrechen”  
 Die letzten Elemente im zusammengesetzten Steuerelement sind die **Elemente OK** und **Cancel,** <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Grid>die die ersten beiden Spalten der letzten Zeile des belegen. Diese Elemente verwenden einen `ButtonClicked`allgemeinen Ereignishandler <xref:System.Windows.Controls.Button> , und den Standardstil, der im vorherigen XAML definiert wurde.  
  
 Fügen Sie in MyControl1.xaml das folgende <xref:System.Windows.Controls.TextBox> XAML nach dem letzten Element hinzu. Der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Teil des zusammengesetzten Steuerelements ist nun abgeschlossen.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementieren der CodeBehind-Datei  
 Die CodeBehind-Datei MyControl1.xaml.cs implementiert drei wesentliche Aufgaben:
  
1. Sie behandelt das Ereignis, das auftritt, wenn der Benutzer eine der Schaltflächen klickt.  
  
2. Ruft die Daten <xref:System.Windows.Controls.TextBox> aus den Elementen ab und verpackt sie in einem benutzerdefinierten Ereignisargumentobjekt.  
  
3. Löst das `OnButtonClick` benutzerdefinierte Ereignis aus, das den Host benachrichtigt, dass der Benutzer fertig ist, und die Daten an den Host zurückgibt.  
  
 Das Steuerelement macht auch eine Reihe von Farb- und Schriftart-Eigenschaften verfügbar, mit deren Hilfe Sie das Erscheinungsbild anpassen können. Im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Gegensatz zur Klasse, die zum Hosten <xref:System.Windows.Forms.Integration.ElementHost> eines Windows Forms-Steuerelements verwendet wird, macht die Klasse nur die Eigenschaft des Steuerelements <xref:System.Windows.Controls.Panel.Background%2A> verfügbar. Um die Ähnlichkeit zwischen diesem Codebeispiel und dem in der exemplarischen Vorgehensweise beschriebenen [Beispiel: Hosten eines Windows Forms Composite-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)beizubehalten, macht das Steuerelement die verbleibenden Eigenschaften direkt verfügbar.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Die grundlegende Struktur der CodeBehind-Datei  
 Die CodeBehind-Datei besteht aus einem `MyControls`einzelnen Namespace , `MyControl1` `MyControlEventArgs`der zwei Klassen enthält, und .  
  
```csharp  
namespace MyControls  
{  
  public partial class MyControl1 : Grid  
  {  
    //...  
  }  
  public class MyControlEventArgs : EventArgs  
  {  
    //...  
  }  
}  
```  
  
 Die erste `MyControl1`Klasse , , ist eine partielle Klasse, die den Code enthält, der die Funktionalität der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in MyControl1.xaml definierten implementiert. Wenn MyControl1.xaml analysiert wird, wird die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in dieselbe partielle Klasse konvertiert, und die beiden partiellen Klassen werden zu dem kompilierten Steuerelement zusammengeführt. Aus diesem Grund muss der Klassenname in der CodeBehind-Datei mit dem übereinstimmen, der MyControl1.xaml zugewiesen wurde, und er muss vom Stammelement des Steuerelements erben. Die zweite `MyControlEventArgs`Klasse , ist eine Ereignisargumentklasse, die verwendet wird, um die Daten an den Host zurückzusenden.  
  
 Öffnen Sie "MyControl1.xaml.cs". Ändern Sie die vorhandene Klassendeklaration so, dass <xref:System.Windows.Controls.Grid>sie den folgenden Namen hat und von erbt.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Initialisieren des Steuerelements  
 Im folgenden Code werden mehrere grundlegende Aufgaben implementiert:  
  
- Deklariert ein privates Ereignis , `OnButtonClick` `MyControlEventHandler`und den zugehörigen Delegaten , .  
  
- Erstellen von mehreren privaten globalen Variablen, welche die Benutzerdaten speichern. Diese Daten werden durch entsprechende Eigenschaften verfügbar gemacht.  
  
- Implementiert einen Handler, `Init`, für <xref:System.Windows.FrameworkElement.Loaded> das Ereignis des Steuerelements. Dieser Handler initialisiert die globalen Variablen, indem er ihnen die in MyControl1.xaml definierten Werte zuweist. Dazu wird das <xref:System.Windows.FrameworkElement.Name%2A> einem typischen <xref:System.Windows.Controls.TextBlock> Element `nameLabel`zugewiesene verwendet, um auf die Eigenschafteneinstellungen dieses Elements zuzugreifen.  
  
 Löschen Sie den vorhandenen Konstruktor, `MyControl1` und fügen Sie der Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Behandeln der Click-Ereignisse der Schaltflächen  
 Der Benutzer gibt an, dass die Dateneingabeaufgabe abgeschlossen ist, indem er entweder auf die Schaltfläche **OK** oder die Schaltfläche **Abbrechen** klickt. Beide Schaltflächen <xref:System.Windows.Controls.Primitives.ButtonBase.Click> verwenden denselben `ButtonClicked`Ereignishandler. Beide Schaltflächen haben `btnOK` `btnCancel`einen Namen oder , der es dem Handler ermöglicht, `sender` zu bestimmen, auf welche Schaltfläche geklickt wurde, indem der Wert des Arguments untersucht wird. Der Handler führt die folgenden Aktionen aus:  
  
- Erstellt `MyControlEventArgs` ein Objekt, das <xref:System.Windows.Controls.TextBox> die Daten aus den Elementen enthält.  
  
- Wenn der Benutzer **Cancel** auf die Schaltfläche `MyControlEventArgs` Abbrechen `IsOK` geklickt hat, wird die Eigenschaft des Objekts auf `false`festgelegt.  
  
- Löst `OnButtonClick` das Ereignis aus, um dem Host anzuzeigen, dass der Benutzer fertig ist, und gibt die gesammelten Daten zurück.  
  
 Fügen Sie der `MyControl1` Klasse nach `Init` der Methode den folgenden Code hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Erstellen von Eigenschaften  
 Der Rest der Klasse macht lediglich Eigenschaften verfügbar, die den oben erläuterten globalen Variablen entsprechen. Wenn sich eine Eigenschaft ändert, passt der Set-Accessor das Erscheinungsbild des Steuerelements an, indem er die entsprechenden Elementeigenschaften und die zugrunde liegenden globalen Variablen aktualisiert.  
  
 Fügen Sie der `MyControl1` Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Zurücksenden der Daten an den Host  
 Die letzte Komponente in `MyControlEventArgs` der Datei ist die Klasse, die verwendet wird, um die gesammelten Daten an den Host zurückzusenden.  
  
 Fügen Sie den `MyControls` folgenden Code zu Ihrem Namespace hinzu. Die Implementierung ist einfach und wird nicht weiter erläutert.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Erstellen Sie die Projektmappe. Der Build erzeugt eine DLL mit dem Namen MyControls.dll.  
  
<a name="winforms_host_section"></a>
## <a name="implementing-the-windows-forms-host-application"></a>Implementieren der Windows Forms-Hostanwendung  
 Die Windows Forms-Hostanwendung verwendet <xref:System.Windows.Forms.Integration.ElementHost> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Objekt zum Hosten des zusammengesetzten Steuerelements. Die Anwendung behandelt `OnButtonClick` das Ereignis, um die Daten vom zusammengesetzten Steuerelement zu empfangen. Die Anwendung verfügt auch über eine Reihe von Optionsfeldern, mit denen Sie die Darstellung des Steuerelements ändern können. Die folgende Abbildung zeigt die Anwendung.  

Die folgende Abbildung zeigt ein WPF-Verbundsteuerelement, das in einer Windows Forms-Anwendung gehostet wird."  

 ![Screenshot, der ein Windows Form Hosting Avalon-Steuerelement zeigt.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1. Starten Sie Visual Studio, und öffnen Sie das Dialogfeld **Neues Projekt.**  
  
2. Wählen Sie in Visual C- und der Windows-Kategorie die **Windows Forms-Anwendungsvorlage** aus.  
  
3. Geben Sie dem neuen Projekt den Namen `WFHost`.  
  
4. Geben Sie für den Speicherort denselben Stammordner an, der das Projekt „MyControls” enthält.  
  
5. Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
 Sie müssen auch Verweise auf die `MyControl1` DLL hinzufügen, die und andere Assemblys enthält.  
  
1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektnamen, und wählen Sie **Referenz hinzufügen**aus.  
  
2. Klicken Sie auf die Registerkarte **Durchsuchen,** und navigieren Sie zu dem Ordner, der MyControls.dll enthält. In dieser exemplarischen Vorgehensweise ist dies der Ordner "MyControls\bin\Debug".  
  
3. Wählen Sie MyControls.dll aus, und klicken Sie dann auf **OK**.  
  
4. Fügen Sie Verweise auf die folgenden Assemblys hinzu.  
  
    - PresentationCore  
  
    - PresentationFramework  
  
    - System.Xaml  
  
    - WindowsBase  
  
    - WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>Implementieren der Benutzeroberfläche für die Anwendung  
 Die Benutzeroberfläche für die Windows Forms-Anwendung enthält mehrere Steuerelemente, die dazu dienen, mit dem zusammengesetzten WPF-Steuerelement zu interagieren.  
  
1. Öffnen Sie Form1 im Windows Forms-Designer.  
  
2. Vergrößern Sie das Formular, um den Steuerelementen genügend Platz zu geben.  
  
3. Fügen Sie in der oberen rechten <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> Ecke des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Formulars ein Steuerelement hinzu, das das zusammengesetzte Steuerelement aufhält.  
  
4. Fügen Sie <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> dem Formular die folgenden Steuerelemente hinzu.  
  
    |name|Text|  
    |----------|----------|  
    |groupBox1|Hintergrundfarbe|  
    |groupBox2|Vordergrundfarbe|  
    |groupBox3|Schriftgrad|  
    |groupBox4|Schriftfamilie|  
    |groupBox5|Schriftschnitt|  
    |groupBox6|Schriftbreite|  
    |groupBox7|Daten vom Steuerelement|  
  
5. Fügen Sie <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> den <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> Steuerelementen die folgenden Steuerelemente hinzu.  
  
    |GroupBox|name|Text|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Original|  
    |groupBox1|radioBackgroundLightGreen|Hellgrün|  
    |groupBox1|radioBackgroundLightSalmon|Helles Lachsrot|  
    |groupBox2|radioForegroundOriginal|Original|  
    |groupBox2|radioForegroundRed|Red|  
    |groupBox2|radioForegroundYellow|Gelb|  
    |groupBox3|radioSizeOriginal|Original|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|Original|  
    |groupBox4|radioFamilyTimes|Times New Roman|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|Normal|  
    |groupBox5|radioStyleItalic|Kursiv|  
    |groupBox6|radioWeightOriginal|Original|  
    |groupBox6|radioWeightBold|Fett|  
  
6. Fügen Sie <xref:System.Windows.Forms.Label?displayProperty=nameWithType> die folgenden <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>Steuerelemente zum letzten hinzu. Diese Steuerelemente zeigen die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vom zusammengesetzten Steuerelement zurückgegebenen Daten an.  
  
    |GroupBox|name|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Name:|  
    |groupBox7|lblAddress|Straße und Hausnummer:|  
    |groupBox7|lblCity|Ort:|  
    |groupBox7|lblState|Status:|  
    |groupBox7|lblZip|Postleitzahl:|  
  
### <a name="initializing-the-form"></a>Initialisieren des Formulars  
 Im Allgemeinen implementieren Sie den Hostingcode im Ereignishandler des Formulars. <xref:System.Windows.Forms.Form.Load> Der folgende Code <xref:System.Windows.Forms.Form.Load> zeigt den Ereignishandler, einen Handler für das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignis des zusammengesetzten Steuerelements <xref:System.Windows.FrameworkElement.Loaded> und Deklarationen für mehrere globale Variablen, die später verwendet werden.  
  
 Doppelklicken Sie im Windows Forms Designer auf <xref:System.Windows.Forms.Form.Load> das Formular, um einen Ereignishandler zu erstellen. Fügen Sie oben in Form1.cs `using` die folgenden Anweisungen hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Ersetzen Sie den `Form1` Inhalt der vorhandenen Klasse durch den folgenden Code.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Die `Form1_Load` Methode im vorherigen Code zeigt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] allgemeine Prozedur zum Hosten eines Steuerelements:  
  
1. Erstellen Sie ein neues <xref:System.Windows.Forms.Integration.ElementHost>-Objekt.  
  
2. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>des Steuerelements auf .  
  
3. Fügen <xref:System.Windows.Forms.Integration.ElementHost> Sie das <xref:System.Windows.Forms.Panel> Steuerelement <xref:System.Windows.Forms.Control.Controls%2A> der Auflistung des Steuerelements hinzu.  
  
4. Erstellen Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Instanz des Steuerelements.  
  
5. Hosten Sie das zusammengesetzte Steuerelement im <xref:System.Windows.Forms.Integration.ElementHost> Formular, <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> indem Sie das Steuerelement der Eigenschaft des Steuerelements zuweisen.  
  
 Die verbleibenden zwei `Form1_Load` Zeilen in der Methode fügen Handler an zwei Steuerelementereignisse an:  
  
- `OnButtonClick`ist ein benutzerdefiniertes Ereignis, das vom zusammengesetzten Steuerelement ausgelöst wird, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt. Behandeln Sie dieses Ereignis, um die Antwort des Benutzers zu erhalten und alle vom Benutzer angegebenen Daten zu erfassen.  
  
- <xref:System.Windows.FrameworkElement.Loaded>ist ein Standardereignis, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von einem Steuerelement ausgelöst wird, wenn es vollständig geladen ist. Das Ereignis wird hier verwendet, da dieses Beispiel mehrere globale Variablen mithilfe der Eigenschaften des Steuerelements initialisieren muss. Zum Zeitpunkt des Formularereignisses <xref:System.Windows.Forms.Form.Load> ist das Steuerelement nicht vollständig geladen, `null`und diese Werte sind weiterhin auf festgelegt. Sie müssen warten, bis <xref:System.Windows.FrameworkElement.Loaded> das Ereignis des Steuerelements eintritt, bevor Sie auf diese Eigenschaften zugreifen können.  
  
 Der <xref:System.Windows.FrameworkElement.Loaded> Ereignishandler wird im vorherigen Code angezeigt. Der `OnButtonClick` Handler wird im nächsten Abschnitt erläutert.  
  
### <a name="handling-onbuttonclick"></a>Behandeln von OnButtonClick  
 Das `OnButtonClick` Ereignis tritt auf, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt.  
  
 Der Ereignishandler überprüft das `IsOK` Feld des Ereignisarguments, um zu bestimmen, auf welche Schaltfläche geklickt wurde. Die `lbl` *Datenvariablen* entsprechen <xref:System.Windows.Forms.Label> den Steuerelementen, die zuvor besprochen wurden. Wenn der Benutzer auf die Schaltfläche **OK** klickt, werden die Daten aus den Steuerelementen des Steuerelements <xref:System.Windows.Controls.TextBox> dem entsprechenden <xref:System.Windows.Forms.Label> Steuerelement zugewiesen. Wenn der Benutzer **Cancel**auf <xref:System.Windows.Forms.Label.Text%2A> Abbrechen klickt, werden die Werte auf die Standardzeichenfolgen festgelegt.  
  
 Fügen Sie der `Form1` Klasse den folgenden Schaltflächenklick-Ereignishandlercode hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus. Fügen Sie Text in das WPF-Verbundsteuerelement ein, und klicken Sie dann auf **OK**. Der Text wird in den Beschriftungen angezeigt. Zu diesem Zeitpunkt wurde noch kein Code für die Behandlung der Optionsfelder hinzugefügt.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Ändern des Erscheinungsbilds des Steuerelements  
 Die <xref:System.Windows.Forms.RadioButton> Steuerelemente im Formular ermöglichen es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dem Benutzer, die Vordergrund- und Hintergrundfarben des zusammengesetzten Steuerelements sowie mehrere Schriftarteneigenschaften zu ändern. Die Hintergrundfarbe wird <xref:System.Windows.Forms.Integration.ElementHost> vom Objekt freigestellt. Die übrigen Eigenschaften werden als benutzerdefinierte Eigenschaften des Steuerelements verfügbar gemacht.  
  
 Doppelklicken Sie <xref:System.Windows.Forms.RadioButton> auf jedes Steuerelement <xref:System.Windows.Forms.RadioButton.CheckedChanged> im Formular, um Ereignishandler zu erstellen. Ersetzen <xref:System.Windows.Forms.RadioButton.CheckedChanged> Sie die Ereignishandler durch den folgenden Code.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus. Klicken Sie auf die verschiedenen Optionsfelder, um die Auswirkung auf das zusammengesetzte WPF-Steuerelement zu sehen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines 3D WPF Composite-Steuerelements in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)

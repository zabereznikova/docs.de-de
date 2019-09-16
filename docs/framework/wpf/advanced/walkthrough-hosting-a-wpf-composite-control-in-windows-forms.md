---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: a062095885e6c1fc8816a78847968b1c250eabf8
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991449"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie jedoch eine beträchtliche Investition in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] den Code haben, kann es effektiver sein, die vorhandene [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu erweitern, anstatt Sie von Grund auf neu zu schreiben. Ein häufiges Szenario ist, wenn Sie ein oder mehrere Steuerelemente, die mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementiert werden, in Ihre Windows Forms Anwendung einbetten möchten. Weitere Informationen zum Anpassen von WPF-Steuerelementen finden Sie unter [Anpassung von Steuer](../controls/control-customization.md)Elementen.  
  
 Diese exemplarische Vorgehensweise führt Sie durch eine Anwendung, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die ein zusammengesetztes Steuerelement hostet, um einen Dateneintrag in einer Windows Forms Anwendung auszuführen. Das zusammengesetzte Steuerelement ist in eine DLL verpackt. Dieses allgemeine Verfahren kann für komplexere Anwendungen und Steuerelemente erweitert werden. Diese exemplarische Vorgehensweise ist so konzipiert, dass Sie in Darstellung und [Funktionalität nahezu identisch ist mit exemplarischen Vorgehensweisen: Hosting eines Windows Forms zusammengesetzten Steuer Elements in](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)WPF. Der Hauptunterschied besteht darin, dass das Hosting-Szenario umgekehrt ist.  
  
 Diese exemplarische Vorgehensweise ist in zwei Abschnitte unterteilt. Im ersten Abschnitt wird die Implementierung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetzten Steuer Elements kurz beschrieben. Im zweiten Abschnitt wird ausführlich erläutert, wie Sie das zusammengesetzte Steuerelement in einer Windows Forms Anwendung hosten, Ereignisse vom Steuerelement empfangen und auf einige der Eigenschaften des Steuer Elements zugreifen können.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
- Implementieren des zusammengesetzten WPF-Steuerelements  
  
- Implementieren der Windows Forms-Hostanwendung  
  
 Eine komplette Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms Beispiel](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementieren des zusammengesetzten WPF-Steuerelements  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in diesem Beispiel verwendete zusammengesetzte Steuerelement ist ein einfaches Dateneingabe Formular, das den Namen und die Adresse des Benutzers annimmt. Klickt der Benutzer eine der zwei Schaltflächen, um anzugeben, dass die Aufgabe abgeschlossen ist, löst das Steuerelement ein benutzerdefiniertes Ereignis aus, um diese Informationen an den Host zurückzugeben. Die folgende Abbildung zeigt das gerenderte Steuerelement. 

 Die folgende Abbildung zeigt ein zusammengesetztes WPF-Steuerelement: 

 ![Screenshot, der ein einfaches WPF-Steuerelement anzeigt.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1. Starten [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]Sie, und öffnen Sie das Dialogfeld **Neues Projekt** .  
  
2. Wählen Sie C# in der Kategorie "Visual" und "Windows" die Vorlage **WPF-Benutzer Steuerelement Bibliothek** aus.  
  
3. Geben Sie dem neuen Projekt den Namen `MyControls`.  
  
4. Geben Sie für den Speicherort einen komfortabel benannten Ordner der obersten Ebene an, `WindowsFormsHostingWpfControl`z. b. Sie werden die Host-Anwendung später in diesem Ordner ablegen.  
  
5. Klicken Sie auf **OK**, um das Projekt zu erstellen. Das Standard Projekt enthält ein einzelnes Steuerelement `UserControl1`mit dem Namen.  
  
6. Benennen `UserControl1` Sie in Projektmappen-Explorer in `MyControl1`um.  
  
 Das Projekt sollte Verweise auf die folgenden System-DLLs aufweisen. Sollten eine oder mehrere dieser DLLs nicht standardmäßig enthalten sein, fügen Sie diese manuell zum Projekt hinzu.  
  
- PresentationCore  
  
- PresentationFramework  
  
- System  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Erstellen der Benutzeroberfläche  
 Der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für das zusammengesetzte Steuerelement wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]mit implementiert. Das zusammengesetzte [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelement besteht <xref:System.Windows.Controls.TextBox> aus fünf Elementen. Jedes <xref:System.Windows.Controls.TextBox> Element verfügt über <xref:System.Windows.Controls.TextBlock> ein zugeordnetes Element, das als Bezeichnung fungiert. Unten sind zwei <xref:System.Windows.Controls.Button> Elemente vorhanden: **OK** und **Abbrechen**. Wenn der Benutzer auf eine Schaltfläche klickt, löst das Steuerelement ein benutzerdefiniertes Ereignis aus, um die Informationen an den Host zurückzugeben.  
  
#### <a name="basic-layout"></a>Grundlegendes Layout  
 Die verschiedenen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Elemente sind in einem <xref:System.Windows.Controls.Grid> -Element enthalten. Sie können verwenden <xref:System.Windows.Controls.Grid> , um den Inhalt des zusammengesetzten Steuer Elements auf die gleiche Weise wie ein `Table` -Element in HTML anzuordnen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verfügt auch über <xref:System.Windows.Documents.Table> ein-Element <xref:System.Windows.Controls.Grid> , ist jedoch einfacher und für einfache Layoutaufgaben besser geeignet.  
  
 Das grundlegende Layout ist im nachfolgenden XAML-Code beschrieben. Dieser XAML-Code definiert die allgemeine Struktur des Steuer <xref:System.Windows.Controls.Grid> Elements, indem die Anzahl der Spalten und Zeilen im-Element angegeben wird.  
  
 Ersetzen Sie in MyControl1.xaml den vorhandenen XAML-Code durch den folgenden.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>TextBlock- und TextBox-Elemente zum Raster hinzufügen  
 Wenn Sie ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Element im Raster platzieren, legen Sie die <xref:System.Windows.Controls.Grid.RowProperty> - <xref:System.Windows.Controls.Grid.ColumnProperty> und-Attribute des Elements auf die entsprechende Zeilen-und Spaltennummer fest. Denken Sie daran, dass die Nummerierungen der Zeilen und Spalten nullbasiert sind. Sie können ein Element über mehrere Spalten verfügen, indem Sie <xref:System.Windows.Controls.Grid.ColumnSpanProperty> das zugehörige-Attribut festlegen. Weitere Informationen zu <xref:System.Windows.Controls.Grid> Elementen finden Sie unter [Erstellen eines Grid-Elements](../controls/how-to-create-a-grid-element.md).  
  
 Der folgende <xref:System.Windows.Controls.TextBox> XAML-Code zeigt die Elemente und <xref:System.Windows.Controls.TextBlock> des zusammengesetzten Steuer Elements mit Ihren <xref:System.Windows.Controls.Grid.RowProperty> -und- <xref:System.Windows.Controls.Grid.ColumnProperty> Attributen, die festgelegt werden, um die Elemente ordnungsgemäß im Raster zu platzieren.  
  
 Fügen Sie in MyControl1. XAML im- <xref:System.Windows.Controls.Grid> Element den folgenden XAML-Code hinzu.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Formatieren der Benutzeroberflächenelemente  
 Viele der Elemente auf dem Dateneingabeformular verfügen über ein ähnliches Erscheinungsbild, was bedeutet, dass viele ihrer Eigenschaften identische Einstellungen aufweisen. Anstatt die Attribute jedes Elements separat festzulegen, verwendet <xref:System.Windows.Style> der vorherige XAML-Code-Elemente, um Standard Eigenschafts Einstellungen für Klassen von Elementen zu definieren. Dieser Ansatz reduziert die Komplexität des Steuerelements und ermöglicht es Ihnen, die Darstellung mehrerer Elemente durch ein einziges Stilattribut zu ändern.  
  
 Die <xref:System.Windows.Style> -Elemente sind in der <xref:System.Windows.Controls.Grid> -Eigenschaft <xref:System.Windows.FrameworkElement.Resources%2A> des-Elements enthalten, sodass Sie von allen-Elementen im-Steuerelement verwendet werden können. Wenn ein Stil benannt wird, wenden Sie ihn auf ein Element an, indem <xref:System.Windows.Style> Sie ein-Element hinzufügen, das auf den Namen des Stils festgelegt ist. Unbenannte Stile werden zum Standardstil für das Element. Weitere Informationen zu Stilen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter Erstellen von Formaten [und](../controls/styling-and-templating.md)Vorlagen.  
  
 Der folgende XAML-Code <xref:System.Windows.Style> zeigt die Elemente für das zusammengesetzte Steuerelement an. Wie die Stile auf Elemente angewendet werden, können Sie dem vorherigen XAML-Code entnehmen. Beispielsweise hat das letzte <xref:System.Windows.Controls.TextBlock> Element den `inlineText` Stil, und das letzte <xref:System.Windows.Controls.TextBox> Element verwendet den Standardstil.  
  
 Fügen Sie in MyControl1. XAML den folgenden XAML-Code direkt <xref:System.Windows.Controls.Grid> nach dem Start-Element hinzu.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Hinzufügen der Schaltflächen „OK” und „Abbrechen”  
 Die letzten Elemente des zusammengesetzten Steuer Elements sind die Elemente " **OK** " und " **Cancel** <xref:System.Windows.Controls.Button> ", die die ersten beiden Spalten <xref:System.Windows.Controls.Grid>der letzten Zeile des belegen. Diese Elemente verwenden einen allgemeinen Ereignishandler, `ButtonClicked`und den im vorherigen <xref:System.Windows.Controls.Button> XAML-Code definierten Standardstil.  
  
 Fügen Sie in MyControl1. XAML den folgenden XAML-Code nach <xref:System.Windows.Controls.TextBox> dem letzten-Element hinzu. Der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Teil des zusammengesetzten Steuer Elements ist jetzt fertiggestellt.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementieren der CodeBehind-Datei  
 Die Code-Behind-Datei MyControl1.XAML.cs implementiert drei wesentliche Aufgaben:
  
1. Sie behandelt das Ereignis, das auftritt, wenn der Benutzer eine der Schaltflächen klickt.  
  
2. Ruft die Daten aus den <xref:System.Windows.Controls.TextBox> Elementen ab und verpackt Sie in einem benutzerdefinierten Ereignis Argument Objekt.  
  
3. Löst das Benutzer `OnButtonClick` definierte Ereignis aus, das den Host benachrichtigt, dass der Benutzer fertig ist, und übergibt die Daten zurück an den Host.  
  
 Das Steuerelement macht auch eine Reihe von Farb- und Schriftart-Eigenschaften verfügbar, mit deren Hilfe Sie das Erscheinungsbild anpassen können. Anders als <xref:System.Windows.Forms.Integration.WindowsFormsHost> die-Klasse, die zum Hosten eines Windows Forms-Steuer <xref:System.Windows.Forms.Integration.ElementHost> Elements verwendet wird, macht <xref:System.Windows.Controls.Panel.Background%2A> die-Klasse die-Eigenschaft des Steuer Elements nur verfügbar So behalten Sie die Ähnlichkeit zwischen diesem Codebeispiel und dem in exemplarischen Vorgehensweise beschriebenen Beispiel bei [ Das-Steuerelement, das ein Windows Forms](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)zusammengesetztes Steuerelement in WPF gehostet, stellt die restlichen Eigenschaften direkt bereit  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Die grundlegende Struktur der CodeBehind-Datei  
 Die Code-Behind-Datei besteht aus einem einzelnen Namespace `MyControls`,, der zwei Klassen enthält, `MyControl1` und `MyControlEventArgs`.  
  
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
  
 Die erste Klasse, `MyControl1`, ist eine partielle Klasse, die den Code enthält, der die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Funktionalität des implementiert, der in MyControl1. XAML definiert ist. Wenn MyControl1. XAML analysiert wird, wird der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in dieselbe partielle Klasse konvertiert, und die beiden partiellen Klassen werden zusammengeführt, um das kompilierte Steuerelement zu bilden. Aus diesem Grund muss der Klassenname in der CodeBehind-Datei mit dem übereinstimmen, der MyControl1.xaml zugewiesen wurde, und er muss vom Stammelement des Steuerelements erben. Die zweite Klasse, `MyControlEventArgs`, ist eine Ereignis Argument Klasse, die verwendet wird, um die Daten zurück an den Host zu senden.  
  
 Öffnen Sie "MyControl1.xaml.cs". Ändern Sie die vorhandene Klassen Deklaration so, dass Sie den folgenden Namen hat und <xref:System.Windows.Controls.Grid>von erbt.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Initialisieren des Steuerelements  
 Im folgenden Code werden mehrere grundlegende Aufgaben implementiert:  
  
- Deklariert ein privates Ereignis, `OnButtonClick`, und den zugehörigen `MyControlEventHandler`Delegaten.  
  
- Erstellen von mehreren privaten globalen Variablen, welche die Benutzerdaten speichern. Diese Daten werden durch entsprechende Eigenschaften verfügbar gemacht.  
  
- Implementiert einen Handler, `Init`, für das-Ereignis <xref:System.Windows.FrameworkElement.Loaded> des-Steuer Elements. Dieser Handler initialisiert die globalen Variablen, indem er ihnen die in MyControl1.xaml definierten Werte zuweist. Zu diesem Zweck verwendet er das <xref:System.Windows.FrameworkElement.Name%2A> einem typischen <xref:System.Windows.Controls.TextBlock> Element `nameLabel`zugewiesene,, um auf die Eigenschaften Einstellungen dieses Elements zuzugreifen.  
  
 Löschen Sie den vorhandenen Konstruktor, `MyControl1` und fügen Sie der-Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Behandeln der Click-Ereignisse der Schaltflächen  
 Der Benutzer gibt an, dass der Dateneingabe Vorgang abgeschlossen ist, indem er auf die Schaltfläche **OK** oder auf die Schaltfläche **Abbrechen** klickt. Beide Schaltflächen verwenden denselben <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis `ButtonClicked`Handler. Beide Schaltflächen haben einen Namen `btnOK` , `btnCancel`oder, mit dem der Handler ermitteln kann, auf welche Schaltfläche geklickt wurde, indem `sender` er den Wert des Arguments untersucht. Der Handler führt die folgenden Aktionen aus:  
  
- Erstellt ein `MyControlEventArgs` -Objekt, das die Daten aus <xref:System.Windows.Controls.TextBox> den-Elementen enthält.  
  
- Wenn der Benutzer auf die Schaltfläche **Abbrechen** geklickt hat `MyControlEventArgs` , wird `IsOK` die- `false`Eigenschaft des-Objekts auf festgelegt.  
  
- Löst das `OnButtonClick` -Ereignis aus, um dem Host mitzuteilen, dass der Benutzer fertig ist, und gibt die gesammelten Daten zurück.  
  
 Fügen Sie der- `MyControl1` Klasse den folgenden Code nach der `Init` -Methode hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Erstellen von Eigenschaften  
 Der Rest der Klasse macht lediglich Eigenschaften verfügbar, die den oben erläuterten globalen Variablen entsprechen. Wenn sich eine Eigenschaft ändert, passt der Set-Accessor das Erscheinungsbild des Steuerelements an, indem er die entsprechenden Elementeigenschaften und die zugrunde liegenden globalen Variablen aktualisiert.  
  
 Fügen Sie der- `MyControl1` Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Zurücksenden der Daten an den Host  
 Die letzte Komponente in der Datei ist die `MyControlEventArgs` -Klasse, die verwendet wird, um die gesammelten Daten zurück an den Host zu senden.  
  
 Fügen Sie dem `MyControls` Namespace den folgenden Code hinzu. Die Implementierung ist einfach und wird nicht weiter erläutert.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Erstellen Sie die Projektmappe. Der Build erzeugt eine DLL mit dem Namen MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Implementieren der Windows Forms-Hostanwendung  
 Die Windows Forms Host Anwendung verwendet ein <xref:System.Windows.Forms.Integration.ElementHost> -Objekt, um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das zusammengesetzte Steuerelement zu hosten. Die Anwendung behandelt das `OnButtonClick` -Ereignis, um die Daten vom zusammengesetzten Steuerelement zu empfangen. Die Anwendung verfügt außerdem über eine Reihe von Optionsfeldern, die Sie verwenden können, um die Darstellung des Steuerelements zu ändern. Die folgende Abbildung zeigt die Anwendung.  

Die folgende Abbildung zeigt ein zusammengesetztes WPF-Steuerelement, das in einer Windows Forms Anwendung gehostet wird.  

 ![Scteenshot zeigt ein Windows Form, das das Avalon-Steuerelement hostet.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Erstellen des Projekts  
 Um das Projekt zu starten:  
  
1. Starten [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]Sie, und öffnen Sie das Dialogfeld **Neues Projekt** .  
  
2. Wählen Sie C# in der Kategorie Visual und Windows die Vorlage **Windows Forms Anwendung** aus.  
  
3. Geben Sie dem neuen Projekt den Namen `WFHost`.  
  
4. Geben Sie für den Speicherort denselben Stammordner an, der das Projekt „MyControls” enthält.  
  
5. Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
 Außerdem müssen Sie Verweise auf die dll hinzufügen, die `MyControl1` und andere Assemblys enthält.  
  
1. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf den Projektnamen, und wählen Sie **Verweis hinzufügen**.  
  
2. Klicken Sie auf die Registerkarte **Durchsuchen** , und navigieren Sie zu dem Ordner, der MyControls. dll enthält. In dieser exemplarischen Vorgehensweise ist dies der Ordner "MyControls\bin\Debug".  
  
3. Wählen Sie MyControls. dll aus, und klicken Sie dann auf **OK**.  
  
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
  
3. Fügen Sie in der oberen rechten Ecke des Formulars ein <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> -Steuerelement hinzu, das das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetzte Steuerelement enthalten soll.  
  
4. Fügen Sie dem <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> Formular die folgenden Steuerelemente hinzu.  
  
    |Name|Text|  
    |----------|----------|  
    |groupBox1|Hintergrundfarbe|  
    |groupBox2|Vordergrundfarbe|  
    |groupBox3|Schriftgrad|  
    |groupBox4|Schriftfamilie|  
    |groupBox5|Schriftschnitt|  
    |groupBox6|Schriftbreite|  
    |groupBox7|Daten vom Steuerelement|  
  
5. Fügen Sie den <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> -Steuer <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> Elementen die folgenden Steuerelemente hinzu.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Ursprünglich|  
    |groupBox1|radioBackgroundLightGreen|Hellgrün|  
    |groupBox1|radioBackgroundLightSalmon|Helles Lachsrot|  
    |groupBox2|radioForegroundOriginal|Ursprünglich|  
    |groupBox2|radioForegroundRed|Rot|  
    |groupBox2|radioForegroundYellow|Gelb|  
    |groupBox3|radioSizeOriginal|Ursprünglich|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|Ursprünglich|  
    |groupBox4|radioFamilyTimes|Times New Roman|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|Normal|  
    |groupBox5|radioStyleItalic|Kursiv|  
    |groupBox6|radioWeightOriginal|Ursprünglich|  
    |groupBox6|radioWeightBold|Bold|  
  
6. Fügen Sie der <xref:System.Windows.Forms.Label?displayProperty=nameWithType> letzten <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>die folgenden Steuerelemente hinzu. Diese Steuerelemente zeigen die vom zusammen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gesetzten Steuerelement zurückgegebenen Daten an.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Name:|  
    |groupBox7|lblAddress|Straße und Hausnummer:|  
    |groupBox7|lblCity|Ort:|  
    |groupBox7|lblState|Zustand:|  
    |groupBox7|lblZip|Postleitzahl:|  
  
### <a name="initializing-the-form"></a>Initialisieren des Formulars  
 Im Allgemeinen implementieren Sie den Hostingcode im- <xref:System.Windows.Forms.Form.Load> Ereignishandler des Formulars. Der folgende Code zeigt den <xref:System.Windows.Forms.Form.Load> Ereignishandler, einen Handler für das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] - <xref:System.Windows.FrameworkElement.Loaded> Ereignis des zusammengesetzten Steuer Elements und-Deklarationen für mehrere globale Variablen, die später verwendet werden.  
  
 Doppelklicken Sie im Windows Forms-Designer auf das Formular, um einen <xref:System.Windows.Forms.Form.Load> -Ereignishandler zu erstellen. Fügen Sie am Anfang von Form1.cs die folgenden `using` -Anweisungen hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Ersetzen Sie den Inhalt der vorhandenen `Form1` -Klasse durch den folgenden Code.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Die `Form1_Load` -Methode im vorangehenden Code zeigt das allgemeine Verfahren zum Hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eines-Steuer Elements:  
  
1. Erstellen Sie ein <xref:System.Windows.Forms.Integration.ElementHost> neues-Objekt.  
  
2. Legen Sie die- <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft des <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>-Steuer Elements auf fest.  
  
3. Fügen Sie <xref:System.Windows.Forms.Integration.ElementHost> das Steuerelement <xref:System.Windows.Forms.Panel> zur- <xref:System.Windows.Forms.Control.Controls%2A> Auflistung des-Steuer Elements hinzu.  
  
4. Erstellen Sie eine Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuer Elements.  
  
5. Hosten Sie das zusammengesetzte Steuerelement auf dem Formular, indem <xref:System.Windows.Forms.Integration.ElementHost> Sie das <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> Steuerelement der-Eigenschaft des Steuer Elements zuweisen  
  
 Die verbleibenden zwei Zeilen in `Form1_Load` der-Methode fügen Handler an zwei Steuerelement Ereignisse an:  
  
- `OnButtonClick`ein benutzerdefiniertes Ereignis, das vom zusammengesetzten Steuerelement ausgelöst wird, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt. Behandeln Sie dieses Ereignis, um die Antwort des Benutzers zu erhalten und alle vom Benutzer angegebenen Daten zu erfassen.  
  
- <xref:System.Windows.FrameworkElement.Loaded>ist ein Standard Ereignis, das von einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Steuerelement ausgelöst wird, wenn es vollständig geladen ist. Das Ereignis wird hier verwendet, da dieses Beispiel mehrere globale Variablen mithilfe der Eigenschaften des Steuerelements initialisieren muss. Zum Zeitpunkt des-Ereignisses des Formulars <xref:System.Windows.Forms.Form.Load> ist das-Steuerelement nicht vollständig geladen, und diese Werte sind immer `null`noch auf festgelegt. Sie müssen warten, bis das- <xref:System.Windows.FrameworkElement.Loaded> Ereignis des-Steuer Elements auftritt, bevor Sie auf diese Eigenschaften zugreifen können.  
  
 Der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler wird im vorangehenden Code gezeigt. Der `OnButtonClick` -Handler wird im nächsten Abschnitt erläutert.  
  
### <a name="handling-onbuttonclick"></a>Behandeln von OnButtonClick  
 Das `OnButtonClick` Ereignis tritt auf, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt.  
  
 Der Ereignishandler überprüft das `IsOK` Feld des Ereignis Arguments, um zu bestimmen, auf welche Schaltfläche geklickt wurde. Die `lbl` *Daten* Variablen entsprechen den <xref:System.Windows.Forms.Label> Steuerelementen, die bereits erläutert wurden. Wenn der Benutzer auf die Schaltfläche **OK** klickt, werden die Daten aus <xref:System.Windows.Controls.TextBox> den Steuerelementen des Steuer Elements <xref:System.Windows.Forms.Label> dem entsprechenden Steuerelement zugewiesen. Wenn der Benutzer auf **Abbrechen**klickt, <xref:System.Windows.Forms.Label.Text%2A> werden die Werte auf die Standard Zeichenfolgen festgelegt.  
  
 Fügen Sie der- `Form1` Klasse den folgenden Button Click-Ereignishandlercode hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus. Fügen Sie Text im zusammengesetzten WPF-Steuerelement hinzu, und klicken Sie dann auf **OK**. Der Text wird in den Beschriftungen angezeigt. Zu diesem Zeitpunkt wurde noch kein Code für die Behandlung der Optionsfelder hinzugefügt.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Ändern des Erscheinungsbilds des Steuerelements  
 Die <xref:System.Windows.Forms.RadioButton> Steuerelemente auf dem Formular ermöglichen dem Benutzer das Ändern der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Vordergrund-und Hintergrundfarben des zusammengesetzten Steuer Elements sowie mehrerer Schriftart Eigenschaften. Die Hintergrundfarbe wird vom <xref:System.Windows.Forms.Integration.ElementHost> -Objekt verfügbar gemacht. Die übrigen Eigenschaften werden als benutzerdefinierte Eigenschaften des Steuerelements verfügbar gemacht.  
  
 Doppelklicken Sie auf <xref:System.Windows.Forms.RadioButton> jedes Steuerelement im Formular, <xref:System.Windows.Forms.RadioButton.CheckedChanged> um Ereignishandler zu erstellen. Ersetzen Sie <xref:System.Windows.Forms.RadioButton.CheckedChanged> die Ereignishandler durch den folgenden Code.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus. Klicken Sie auf die verschiedenen Optionsfelder, um die Auswirkung auf das zusammengesetzte WPF-Steuerelement zu sehen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosting eines Windows Forms zusammengesetzten Steuer Elements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosting eines zusammengesetzten 3D-WPF-Steuer Elements in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)

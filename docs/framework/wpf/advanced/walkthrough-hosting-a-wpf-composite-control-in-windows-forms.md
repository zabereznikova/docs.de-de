---
title: "Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Hosten von WPF-Inhalt in Windows Forms"
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit.  Wenn Sie allerdings bereits erheblichen Aufwand für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Code betrieben haben, kann es effektiver sein, eine vorhandene [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Anwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu erweitern, anstatt sie von Grund auf neu zu schreiben.  Ein häufiges Szenario ist das Einbetten eines oder mehrerer mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementierter Steuerelemente in die [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Anwendung.  Weitere Informationen zum Anpassen von WPF\-Steuerelementen finden Sie unter [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md).  
  
 In dieser exemplarischen Vorgehensweise wird eine Anwendung vorgestellt, die ein zusammengesetztes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement hostet, um die Dateneingabe in einer [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Anwendung auszuführen.  Das zusammengesetzte Steuerelement ist in einer DLL gepackt.  Diese allgemeine Prozedur kann auf komplexere Anwendungen und Steuerelemente erweitert werden.  Diese exemplarische Vorgehensweise ist hinsichtlich Darstellung und Funktionalität nahezu identisch mit [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md).  Der Hauptunterschied liegt in einer Umkehrung des Hostingszenarios.  
  
 Die exemplarische Vorgehensweise ist in zwei Abschnitte unterteilt.  Im ersten Abschnitt wird kurz die Implementierung des zusammengesetzten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelements beschrieben.  Im zweiten Abschnitt wird detailliert erläutert, wie das zusammengesetzte Steuerelement in einer [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Anwendung gehostet wird, Ereignisse vom Steuerelement empfangen werden und auf einige Eigenschaften des Steuerelements zugegriffen wird.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Implementieren des zusammengesetzten WPF\-Steuerelements  
  
-   Implementieren der Windows Forms\-Hostanwendung  
  
 Eine vollständige Codeauflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht wurden, finden Sie unter [Beispiel zum Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](http://go.microsoft.com/fwlink/?LinkID=159996).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Implementieren des zusammengesetzten WPF\-Steuerelements  
 Das in diesem Beispiel verwendete zusammengesetzte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement ist ein einfaches Dateneingabeformular, in das der Name und die Adresse des Benutzers eingegeben werden.  Wenn der Benutzer auf eine der zwei Schaltflächen klickt, um anzuzeigen, dass die Aufgabe beendet ist, löst das Steuerelement ein benutzerdefiniertes Ereignis aus, um diese Informationen an den Host zurückzugeben.  Die folgende Abbildung zeigt das gerenderte Steuerelement.  
  
 ![Einfaches WPF&#45;Steuerelement](../../../../docs/framework/wpf/advanced/media/avaloncontrol.png "AvalonControl")  
Zusammengesetztes WPF\-Steuerelement  
  
### Erstellen des Projekts  
 So starten Sie das Projekt  
  
1.  Starten Sie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], und öffnen Sie das Dialogfeld **Neues Projekt**.  
  
2.  Wählen Sie in Visual C\# und der Windows\-Kategorie die Vorlage **WPF\-Benutzersteuerelementbibliothek** aus.  
  
3.  Geben Sie für das neue Projekt den Namen `MyControls` ein.  
  
4.  Geben Sie für den Speicherort einen passend benannten Ordner der obersten Ebene an, z. B. `WindowsFormsHostingWpfControl`.  Später legen Sie die Hostanwendung in diesem Ordner ab.  
  
5.  Klicken Sie auf **OK**, um das Projekt zu erstellen.  Das Standardprojekt enthält ein einzelnes Steuerelement mit dem Namen `UserControl1`.  
  
6.  Benennen Sie im Projektmappen\-Explorer `UserControl1` in `MyControl1` um.  
  
 Das Projekt sollte Verweise auf die folgenden System\-DLLs aufweisen.  Wenn diese DLLs nicht standardmäßig enthalten sind, fügen Sie sie dem Projekt hinzu.  
  
-   PresentationCore  
  
-   PresentationFramework  
  
-   System  
  
-   WindowsBase  
  
### Erstellen der Benutzeroberfläche  
 Die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für das zusammengesetzte Steuerelement wird mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] implementiert.  Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] des zusammengesetzten Steuerelements besteht aus fünf <xref:System.Windows.Controls.TextBox>\-Elementen.  Jedes <xref:System.Windows.Controls.TextBox>\-Element verfügt über ein zugeordnetes <xref:System.Windows.Controls.TextBlock>\-Element, das als Bezeichnung dient.  Zwei <xref:System.Windows.Controls.Button>\-Elemente befinden sich im unteren Bereich: **OK** und **Abbrechen**.  Wenn der Benutzer auf eine der zwei Schaltflächen klickt, löst das Steuerelement ein benutzerdefiniertes Ereignis aus, um die Informationen an den Host zurückzugeben.  
  
#### Grundlegendes Layout  
 Die verschiedenen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente sind in einem <xref:System.Windows.Controls.Grid>\-Element enthalten.  Sie können den Inhalt des zusammengesetzten Steuerelements anordnen, indem Sie das <xref:System.Windows.Controls.Grid>\-Element auf ähnliche Weise verwenden wie ein `Table`\-Element in HTML.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt auch über ein <xref:System.Windows.Documents.Table>\-Element, aber das <xref:System.Windows.Controls.Grid>\-Element ist einfacher und für einfache Layoutaufgaben besser geeignet.  
  
 Das folgende XAML\-Beispiel zeigt das grundlegende Layout.  Dieser XAML\-Code definiert durch Angabe der Anzahl von Spalten und Zeilen im <xref:System.Windows.Controls.Grid>\-Element die Gesamtstruktur des Steuerelements.  
  
 Ersetzen Sie in "MyControl1.xaml" den vorhandenen XAML\-Code durch den folgenden XAML\-Code:  
  
 [!code-xml[WindowsFormsHostingWpfControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xml[WindowsFormsHostingWpfControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### Hinzufügen der Elemente TextBlock und TextBox zum Raster  
 Sie platzieren ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Element im Raster, indem Sie das <xref:System.Windows.Controls.Grid.RowProperty>\-Attribut und das <xref:System.Windows.Controls.Grid.ColumnProperty>\-Attribut des Elements auf die entsprechende Zeilen\- und Spaltennummer festlegen.  Denken Sie daran, dass die Zeilen\- und Spaltennummerierung nullbasiert ist.  Ein Element kann durch Festlegen seines <xref:System.Windows.Controls.Grid.ColumnSpanProperty>\-Attributs mehrere Spalten überspannen.  Weitere Informationen zu <xref:System.Windows.Controls.Grid>\-Elementen finden Sie unter [Erstellen eines Grid\-Elements](../../../../docs/framework/wpf/controls/how-to-create-a-grid-element.md).  
  
 Der folgende XAML\-Code zeigt die <xref:System.Windows.Controls.TextBox>\- und <xref:System.Windows.Controls.TextBlock>\-Elemente des zusammengesetzten Steuerelements mit den <xref:System.Windows.Controls.Grid.RowProperty>\- und <xref:System.Windows.Controls.Grid.ColumnProperty>\-Attributen, die so festgelegt sind, dass die Elemente korrekt im Raster platziert werden.  
  
 Fügen Sie in "MyControl1.xaml" den folgenden XAML\-Code innerhalb des <xref:System.Windows.Controls.Grid>\-Elements hinzu.  
  
 [!code-xml[WindowsFormsHostingWpfControl#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### Formatieren der Benutzeroberflächenelemente  
 Viele Elemente im Dateneingabeformular ähneln einander, d. h. mehrere ihrer Eigenschaften besitzen identische Einstellungen.  Anstatt die Attribute jedes Elements einzeln festzulegen, werden im obigen XAML\-Code mithilfe von <xref:System.Windows.Style>\-Elementen standardmäßige Eigenschafteneinstellungen für Elementklassen definiert.  Dieser Ansatz reduziert die Komplexität des Steuerelements und ermöglicht es Ihnen, die Darstellung mehrerer Elemente durch ein einziges Stilattribut zu ändern.  
  
 Die <xref:System.Windows.Style>\-Elemente sind in der <xref:System.Windows.FrameworkElement.Resources%2A>\-Eigenschaft des <xref:System.Windows.Controls.Grid>\-Elements enthalten, sodass sie von allen Elementen im Steuerelement verwendet werden können.  Wenn ein Stil benannt ist, wird er auf ein Element angewendet, indem dem Stilnamen ein <xref:System.Windows.Style>\-Elementsatz hinzugefügt wird.  Unbenannte Stile werden zum Standardstil für das Element.  Weitere Informationen zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Der folgende XAML\-Code zeigt die <xref:System.Windows.Style>\-Elemente für das zusammengesetzte Steuerelement.  Wie die Stile auf Elemente angewendet werden, sehen Sie im vorherigen XAML\-Code.  Das letzte <xref:System.Windows.Controls.TextBlock>\-Element z. B. hat den `inlineText`\-Stil, und das letzte <xref:System.Windows.Controls.TextBox>\-Element verwendet den Standardstil.  
  
 Fügen Sie in "MyControl1.xaml" den folgenden XAML\-Code direkt nach dem <xref:System.Windows.Controls.Grid>\-Startelement hinzu.  
  
 [!code-xml[WindowsFormsHostingWpfControl#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### Hinzufügen der Schaltflächen "OK" und "Abbrechen"  
 Die letzten Elemente im zusammengesetzten Steuerelement sind die <xref:System.Windows.Controls.Button>\-Elemente **OK** und **Abbrechen**, die die ersten zwei Spalten der letzten Zeile im <xref:System.Windows.Controls.Grid> belegen.  Diese Elemente verwenden den allgemeinen Ereignishandler `ButtonClicked` und den <xref:System.Windows.Controls.Button>\-Standardstil, der im vorherigen XAML\-Code definiert wurde.  
  
 Fügen Sie in "MyControl1.xaml" den folgenden XAML\-Code nach dem letzten <xref:System.Windows.Controls.TextBox>\-Element hinzu.  Der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Teil des zusammengesetzten Steuerelements ist jetzt vollständig.  
  
 [!code-xml[WindowsFormsHostingWpfControl#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### Implementieren der Code\-Behind\-Datei  
 Die CodeBehind\-Datei "MyControl1.xaml.cs" implementiert drei wesentliche Aufgaben:  
  
1.  Behandlung des Ereignisses, das ausgelöst wird, wenn der Benutzer auf eine der Schaltflächen klickt.  
  
2.  Abrufen der Daten von den <xref:System.Windows.Controls.TextBox>\-Elementen und Packen der Daten in ein benutzerdefiniertes Ereignisargumentobjekt.  
  
3.  Auslösen des benutzerdefinierten `OnButtonClick`\-Ereignisses, das den Host benachrichtigt, dass der Benutzer den Vorgang abgeschlossen hat, und das die Daten wieder an den Host übergibt.  
  
 Das Steuerelement macht auch eine Reihe von Farb\- und Schriftarteigenschaften verfügbar, mit denen die Darstellung geändert werden kann.  Im Gegensatz zur <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse, die zum Hosten eines [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelements verwendet wird, macht die <xref:System.Windows.Forms.Integration.ElementHost>\-Klasse nur die <xref:System.Windows.Controls.Panel.Background%2A>\-Eigenschaft des Steuerelements verfügbar.  Um die Ähnlichkeit zwischen diesem Codebeispiel und dem in [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md) erläuterten Beispiel beizubehalten, macht das Steuerelement die übrigen Eigenschaften direkt verfügbar.  
  
#### Grundlegende Struktur der Code\-Behind\-Datei  
 Die CodeBehind\-Datei besteht aus einem einzelnen Namespace `MyControls`, der die zwei Klassen `MyControl1` und `MyControlEventArgs` enthält.  
  
```  
  
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
  
 Die erste Klasse, `MyControl1`, ist eine partielle Klasse mit dem Code, der die Funktionen der in "MyControl1.xaml" definierten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] implementiert.  Wenn "MyControl1.xaml" analysiert wird, wird das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in die gleiche partielle Klasse umgewandelt, und die beiden partiellen Klassen werden zusammengeführt, um das kompilierte Steuerelement zu bilden.  Daher muss der Klassenname in der CodeBehind\-Datei mit dem "MyControl1.xaml" zugewiesenen Klassennamen übereinstimmen, und er muss vom Stammelement des Steuerelements erben.  Die zweite Klasse, `MyControlEventArgs`, ist eine Ereignisklasse für Argumente, die verwendet wird, um die Daten an den Host zurückzusenden.  
  
 Öffnen Sie "MyControl1.xaml.cs".  Ändern Sie die vorhandene Klassendeklaration, sodass sie den folgenden Namen aufweist und von <xref:System.Windows.Controls.Grid> erbt.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### Initialisieren des Steuerelements  
 Im folgenden Code werden mehrere grundlegende Aufgaben implementiert:  
  
-   Deklarieren des privaten Ereignisses `OnButtonClick` und seines zugeordneten Delegaten `MyControlEventHandler`.  
  
-   Erstellen mehrerer privater globaler Variablen, in denen die Benutzerdaten gespeichert werden.  Diese Daten werden durch entsprechende Eigenschaften verfügbar gemacht.  
  
-   Implementieren Sie einen Handler `Init` für das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis des Steuerelements.  Dieser Handler initialisiert die globalen Variablen, indem er ihnen die in "MyControl1.xaml" definierten Werte zuweist.  Dazu verwendet er <xref:System.Windows.FrameworkElement.Name%2A>, der dem normalen <xref:System.Windows.Controls.TextBlock>\-Element `nameLabel` zugewiesen ist, um auf die Eigenschafteneinstellungen dieses Elements zuzugreifen.  
  
 Löschen Sie den vorhandenen Konstruktor, und fügen Sie der `MyControl1`\-Klasse den folgenden Code hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### Behandeln der Klickereignisse der Schaltflächen  
 Der Benutzer zeigt durch Klicken auf die Schaltfläche **OK** oder **Abbrechen** an, dass er die Dateneingabe abgeschlossen hat.  Beide Schaltflächen verwenden denselben <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler, `ButtonClicked`.  Beide Schaltflächen besitzen einen Namen, `btnOK` bzw. `btnCancel`, mit denen der Handler durch Überprüfen des Werts des `sender`\-Arguments feststellen kann, auf welche Schaltfläche geklickt wurde.  Der Handler führt folgende Aufgaben aus:  
  
-   Erstellen eines `MyControlEventArgs`\-Objekts, das die Daten der <xref:System.Windows.Controls.TextBox>\-Elemente enthält.  
  
-   Festlegen der `IsOK`\-Eigenschaft des `MyControlEventArgs`\-Objekts auf `false`, wenn der Benutzer auf die Schaltfläche **Abbrechen** geklickt hat.  
  
-   Auslösen des `OnButtonClick`\-Ereignisses, um dem Host anzuzeigen, dass der Benutzer den Vorgang abgeschlossen hat, und Übergabe der gesammelten Daten.  
  
 Fügen Sie den folgenden Code in der `MyControl1`\-Klasse nach der `Init`\-Methode hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### Erstellen von Eigenschaften  
 Der Rest der Klasse macht einfach Eigenschaften verfügbar, die den oben erläuterten globalen Variablen entsprechen.  Wenn sich eine Eigenschaft ändert, ändert der set\-Accessor die Darstellung des Steuerelements, indem er die entsprechenden Elementeigenschaften ändert und die zugrunde liegenden globalen Variablen aktualisiert.  
  
 Fügen Sie der `MyControl1`\-Klasse folgenden Code hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### Zurücksenden der Daten an den Host  
 Die letzte Komponente in der Datei ist die `MyControlEventArgs`\-Klasse, die verwendet wird, um die gesammelten Daten zurück an den Host zu senden.  
  
 Fügen Sie dem `MyControls`\-Namespace den folgenden Code hinzu.  Die Implementierung ist einfach und wird nicht weiter erläutert.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Erstellen Sie die Projektmappe.  Der Build erzeugt eine DLL mit dem Namen MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## Implementieren der Windows Forms\-Hostanwendung  
 Die [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Hostanwendung verwendet ein <xref:System.Windows.Forms.Integration.ElementHost>\-Objekt zum Hosten des zusammengesetzten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelements.  Die Anwendung behandelt das `OnButtonClick`\-Ereignis, um die Daten vom zusammengesetzten Steuerelement zu empfangen.  Die Anwendung verfügt auch über eine Reihe von Optionsfeldern, mit denen Sie die Darstellung des Steuerelements ändern können.  Die folgende Abbildung zeigt die Anwendung.  
  
 ![Windows Forms Hosting Avalon&#45;Steuerelement](../../../../docs/framework/wpf/advanced/media/wfhost.png "WFHost")  
Zusammengesetztes WPF\-Steuerelement, das in einer Windows Forms\-Anwendung gehostet wird  
  
### Erstellen des Projekts  
 So starten Sie das Projekt  
  
1.  Starten Sie [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], und öffnen Sie das Dialogfeld **Neues Projekt**.  
  
2.  Wählen Sie in Visual C\# und der Windows\-Kategorie die Vorlage **Windows Forms\-Anwendung** aus.  
  
3.  Geben Sie für das neue Projekt den Namen `WFHost` ein.  
  
4.  Geben Sie für den Speicherort den Ordner der obersten Ebene an, der auch das Projekt "MyControls" enthält.  
  
5.  Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
 Außerdem müssen Sie Verweise auf die DLL hinzufügen, die `MyControl1` und andere Assemblys enthält.  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Verweis hinzufügen**.  
  
2.  Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zu dem Ordner, der "MyControls.dll" enthält.  In dieser exemplarischen Vorgehensweise ist dies der Ordner "MyControls\\bin\\Debug".  
  
3.  Wählen Sie "MyControls.dll" aus, und klicken Sie dann auf **OK**.  
  
4.  Fügen Sie Verweise auf die folgenden Assemblys hinzu.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   System.Xaml  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
### Implementieren der Benutzeroberfläche für die Anwendung  
 Die Benutzeroberfläche für die Windows Forms\-Anwendung enthält mehrere Steuerelemente, die mit dem zusammengesetzten WPF\-Steuerelement interagieren.  
  
1.  Öffnen Sie Form1 im Windows Forms\-Designer.  
  
2.  Vergrößern Sie das Formular, sodass ausreichend Platz für die Steuerelemente vorhanden ist.  
  
3.  Fügen Sie in der oberen rechten Ecke des Formulars ein <xref:System.Windows.Forms.Panel?displayProperty=fullName>\-Steuerelement für das zusammengesetzte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement hinzu.  
  
4.  Fügen Sie dem Formular die folgenden <xref:System.Windows.Forms.GroupBox?displayProperty=fullName>\-Steuerelemente hinzu.  
  
    |Name|Text|  
    |----------|----------|  
    |groupBox1|Hintergrundfarbe|  
    |groupBox2|Vordergrundfarbe|  
    |groupBox3|Font Size|  
    |groupBox4|Schriftfamilie|  
    |groupBox5|Schriftschnitt|  
    |groupBox6|Schriftbreite|  
    |groupBox7|Daten vom Steuerelement|  
  
5.  Fügen Sie den <xref:System.Windows.Forms.GroupBox?displayProperty=fullName>\-Steuerelementen die folgenden <xref:System.Windows.Forms.RadioButton?displayProperty=fullName>\-Steuerelemente hinzu.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Ursprünglich|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
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
    |groupBox6|radioWeightBold|Fett|  
  
6.  Fügen Sie dem letzten <xref:System.Windows.Forms.GroupBox?displayProperty=fullName>\-Steuerelement die folgenden <xref:System.Windows.Forms.Label?displayProperty=fullName>\-Steuerelemente hinzu.  Diese Steuerelemente zeigen die vom zusammengesetzten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement zurückgegebenen Daten an.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Name:|  
    |groupBox7|lblAddress|Straße:|  
    |groupBox7|lblCity|Ort:|  
    |groupBox7|lblState|Bundesland:|  
    |groupBox7|lblZip|Postleitzahl:|  
  
### Initialisieren des Formulars  
 Hostcode wird üblicherweise im <xref:System.Windows.Forms.Form.Load>\-Ereignishandler des Formulars implementiert.  Der folgende Code zeigt den <xref:System.Windows.Forms.Form.Load>\-Ereignishandler, einen Handler für das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis des zusammengesetzten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelements und Deklarationen für mehrere globale Variablen, die später verwendet werden.  
  
 Doppelklicken Sie im Windows Forms\-Designer auf das Formular, um einen <xref:System.Windows.Forms.Form.Load>\-Ereignishandler zu erstellen.  Fügen Sie am Anfang von "Form1.cs" die folgenden `using`\-Anweisungen hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Ersetzen Sie den Inhalt der vorhandenen `Form1`\-Klasse durch den folgenden Code:  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Die `Form1_Load`\-Methode im vorangehenden Code zeigt die allgemeine Prozedur zum Hosten eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelements:  
  
1.  Erstellen Sie ein neues <xref:System.Windows.Forms.Integration.ElementHost>\-Objekt.  
  
2.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft des Steuerelements auf <xref:System.Windows.Forms.DockStyle?displayProperty=fullName> fest.  
  
3.  Fügen Sie das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement der <xref:System.Windows.Forms.Control.Controls%2A>\-Auflistung des <xref:System.Windows.Forms.Panel>\-Steuerelements hinzu.  
  
4.  Erstellen Sie eine Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelements.  
  
5.  Hosten Sie das zusammengesetzte Steuerelement im Formular, indem Sie es der <xref:System.Windows.Forms.Integration.ElementHost.Child%2A>\-Eigenschaft des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements zuweisen.  
  
 Durch die übrigen zwei Zeilen in der `Form1_Load`\-Methode werden Handler an zwei Steuerelementereignisse angefügt:  
  
-   `OnButtonClick` ist ein benutzerdefiniertes Ereignis, das vom zusammengesetzten Steuerelement ausgelöst wird, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt.  Das Ereignis wird behandelt, um die Antwort des Benutzers abzurufen und die vom Benutzer eingegebenen Daten zu sammeln.  
  
-   <xref:System.Windows.FrameworkElement.Loaded> ist ein Standardereignis, das von einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement ausgelöst wird, wenn es vollständig geladen wurde.  Hier wird das Ereignis verwendet, da im Beispiel mehrere globale Variablen, die Eigenschaften des Steuerelements verwenden, initialisiert werden müssen.  Zum Zeitpunkt des <xref:System.Windows.Forms.Form.Load>\-Ereignisses des Formulars ist das Steuerelement nicht vollständig geladen, und diese Werte sind immer noch auf `null` festgelegt.  Sie müssen bis zum <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis des Steuerelements warten, bevor Sie auf diese Eigenschaften zugreifen können.  
  
 Der <xref:System.Windows.FrameworkElement.Loaded>\-Ereignishandler wird im vorangehenden Code gezeigt.  Der `OnButtonClick`\-Handler wird im nächsten Abschnitt erläutert.  
  
### Behandeln von OnButtonClick  
 Das `OnButtonClick`\-Ereignis tritt ein, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt.  
  
 Der Ereignishandler überprüft das `IsOK`\-Feld des Ereignisarguments, um zu bestimmen, auf welche Schaltfläche geklickt wurde.  Die `lbl`*data*\-Variablen entsprechen den zuvor erläuterten <xref:System.Windows.Forms.Label>\-Steuerelementen.  Wenn der Benutzer auf die Schaltfläche **OK** geklickt hat, werden die Daten der <xref:System.Windows.Controls.TextBox>\-Steuerelemente des Steuerelements dem entsprechenden <xref:System.Windows.Forms.Label>\-Steuerelement zugewiesen.  Wenn der Benutzer auf **Abbrechen** klickt, werden die <xref:System.Windows.Forms.Label.Text%2A>\-Werte auf die Standardzeichenfolgen festgelegt.  
  
 Fügen Sie der `Form1`\-Klasse den folgen Ereignishandlercode für das Click\-Ereignis hinzu.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus.  Fügen Sie im zusammengesetzten WPF\-Steuerelement Text hinzu, und klicken Sie dann auf **OK**.  Der Text wird in den Beschriftungen angezeigt.  Bisher wurde kein Code zum Behandeln der Optionsfelder hinzugefügt.  
  
### Ändern der Darstellung des Steuerelements  
 Mit den <xref:System.Windows.Forms.RadioButton>\-Steuerelementen des Formulars kann der Benutzer die Vorder\- und Hintergrundfarben des zusammengesetzten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelements und einige Schriftarteigenschaften ändern.  Die Hintergrundfarbe wird durch das <xref:System.Windows.Forms.Integration.ElementHost>\-Objekt verfügbar gemacht.  Die übrigen Eigenschaften werden als benutzerdefinierte Eigenschaften des Steuerelements verfügbar gemacht.  
  
 Doppelklicken Sie auf jedes <xref:System.Windows.Forms.RadioButton>\-Steuerelement im Formular, um <xref:System.Windows.Forms.RadioButton.CheckedChanged>\-Ereignishandler zu erstellen.  Ersetzen Sie die <xref:System.Windows.Forms.RadioButton.CheckedChanged>\-Ereignishandler durch den folgenden Code.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Erstellen Sie die Anwendung, und führen Sie sie aus.  Klicken Sie auf die verschiedenen Optionsfelder, um die Auswirkung auf das zusammengesetzte WPF\-Steuerelement zu überprüfen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D\-WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
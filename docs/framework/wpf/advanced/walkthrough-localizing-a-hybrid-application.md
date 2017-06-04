---
title: "Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Hybridanwendungen [WPF-Interoperabilität]"
  - "Lokalisierung [WPF-Interoperabilität]"
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung
In dieser exemplarischen Vorgehensweise wird erläutert, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elemente in einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-basierten Hybridanwendung lokalisiert werden.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Hostprojekts  
  
-   Hinzufügen von lokalisierbarem Inhalt  
  
-   Aktivieren der Lokalisierung  
  
-   Zuweisen von Ressourcenbezeichnern  
  
-   Das Verwenden des LocBaml\-Tools zum Erzeugen einer Satellitenassembly  
  
 Eine vollständige Codeauflistung der in dieser exemplarischen Vorgehensweise veranschaulichten Aufgaben finden Sie unter [Beispiel zum Lokalisieren einer Hybridanwendung](http://go.microsoft.com/fwlink/?LinkID=160015).  
  
 Am Ende des Prozesses haben Sie eine lokalisierte Hybridanwendung.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Erstellen des Windows Forms\-Hostprojekts  
 Zunächst muss das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Anwendungsprojekt erstellt und ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Element mit Inhalt hinzugefügt werden, den Sie lokalisieren werden.  
  
#### So erstellen Sie das Hostprojekt  
  
1.  Erstellen Sie ein WPF\-Anwendungsprojekt mit dem Namen `LocalizingWpfInWf`.  Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Fügen Sie dem Projekt ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.UserControl>\-Element mit dem Namen `SimpleControl` hinzu.  
  
3.  Verwenden Sie das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement, um auf dem Formular ein `SimpleControl`\-Element zu platzieren.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D\-WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).  
  
## Hinzufügen von lokalisierbarem Inhalt  
 Im nächsten Schritt fügen Sie ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Label\-Steuerelement hinzu und legen den Inhalt des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elements auf eine lokalisierbare Zeichenfolge fest.  
  
#### So fügen Sie lokalisierbaren Inhalt hinzu  
  
1.  Doppelklicken Sie im Projektmappen\-Explorer auf **SimpleControl.xaml**, um die Datei im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] zu öffnen.  
  
2.  Legen Sie den Inhalt des <xref:System.Windows.Controls.Button>\-Steuerelements mit dem folgenden Code fest.  
  
     [!code-xml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  Doppelklicken Sie im Projektmappen\-Explorer auf **Form1**, um das Formular im Windows Forms\-Designer zu öffnen.  
  
4.  Öffnen Sie die Toolbox, und doppelklicken Sie auf **Bezeichnung**, um dem Formular ein Label\-Steuerelement hinzuzufügen.  Legen Sie den Wert der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft auf `"Hello"` fest.  
  
5.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Sowohl das `SimpleControl`\-Element als auch das Label\-Steuerelement zeigen den Text **"Hello"** an.  
  
## Aktivieren der Lokalisierung  
 Der Windows Forms\-Designer stellt Einstellungen bereit, mit denen die Lokalisierung in einer Satellitenassembly aktiviert wird.  
  
#### So aktivieren Sie die Lokalisierung  
  
1.  Doppelklicken Sie im Projektmappen\-Explorer auf **Form1.cs**, um das Formular im Windows Forms\-Designer zu öffnen.  
  
2.  Legen Sie im Eigenschaftenfenster den Wert für die **Localizable**\-Eigenschaft auf `true` fest.  
  
3.  Legen Sie im Eigenschaftenfenster den Wert für die **Language**\-Eigenschaft auf **Spanisch \- Spanien** fest.  
  
4.  Wählen Sie im Windows Forms\-Designer das Label\-Steuerelement aus.  
  
5.  Legen Sie im Eigenschaftenfenster den Wert der <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft auf `"Hola"` fest.  
  
     Dem Projekt wird eine neue Ressourcendatei mit dem Namen Form1.es\-ES.resx hinzugefügt.  
  
6.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **Form1.cs**, und klicken Sie dann auf **Code anzeigen**, um die Datei im Code\-Editor zu öffnen.  
  
7.  Kopieren Sie vor dem Aufruf von `InitializeComponent` den folgenden Code in den `Form1`\-Konstruktor.  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **LocalizingWpfInWf**, und klicken Sie dann auf **Projekt entfernen**.  
  
     Der Projektname ist als **\(nicht verfügbar\)** gekennzeichnet.  
  
9. Klicken Sie mit der rechten Maustaste auf **LocalizingWpfInWf**, und klicken Sie dann auf **LocalizingWpfInWf.csproj bearbeiten**.  
  
     Die Projektdatei wird im Code\-Editor geöffnet.  
  
10. Kopieren Sie die folgende Zeile in die erste `PropertyGroup` in der Projektdatei.  
  
    ```  
    <UICulture>en-US</UICulture>   
    ```  
  
11. Speichern Sie die Projektdatei, und schließen Sie sie dann.  
  
12. Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **LocalizingWpfInWf**, und klicken Sie dann auf **Projekt erneut laden**.  
  
## Zuweisen von Ressourcenbezeichnern  
 Mithilfe von Ressourcenbezeichnern können Sie Ressourcenassemblys den lokalisierbaren Inhalt zuordnen.  Die MsBuild.exe\-Anwendung weist Ressourcenbezeichner automatisch zu, wenn Sie die `updateuid`\-Option angeben.  
  
#### So weisen Sie Ressourcenbezeichner zu  
  
1.  Öffnen Sie im Startmenü die [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]\-Eingabeaufforderung.  
  
2.  Verwenden Sie den folgenden Befehl, um dem lokalisierbaren Inhalt Ressourcenbezeichner zuzuweisen.  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  Doppelklicken Sie im Projektmappen\-Explorer auf **SimpleControl.xaml**, um die Datei im Code\-Editor zu öffnen.  Sie werden feststellen, dass der `msbuild`\-Befehl allen Elementen das `Uid`\-Attribut hinzugefügt hat.  Dies erleichtert die Lokalisierung durch die Zuweisung von Ressourcenbezeichnern.  
  
     [!code-xml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  Drücken Sie F6, um die Projektmappe zu erstellen.  
  
## Verwenden von LocBaml zum Erzeugen einer Satellitenassembly  
 Der lokalisierte Inhalt wird in einer *Satellitenassembly* gespeichert, die nur als Ressource dient.  Verwenden Sie das Befehlszeilentool LocBaml.exe, um eine lokalisierte Assembly für den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt zu erzeugen.  
  
#### So erzeugen Sie eine Satellitenassembly  
  
1.  Kopieren Sie LocBaml.exe in den Ordner obj\\Debug des Projekts.  Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
2.  Verwenden Sie im Eingabeaufforderungsfenster den folgenden Befehl, um Ressourcenzeichenfolgen in eine temporäre Datei zu extrahieren.  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  Öffnen Sie die Datei temp.csv in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] oder einem anderen Text\-Editor.  Ersetzen Sie die Zeichenfolge `"Hello"` durch die spanische Übersetzung `"Hola"`.  
  
4.  Speichern Sie die Datei temp.csv.  
  
5.  Verwenden Sie den folgenden Befehl, um die lokalisierte Ressourcendatei zu generieren.  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     Die Datei LocalizingWpfInWf.g.es\-ES.resources wird im Ordner obj\\Debug erstellt.  
  
6.  Verwenden Sie den folgenden Befehl, um die lokalisierte Satellitenassembly zu erstellen.  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     Die Datei LocalizingWpfInWf.resources.dll wird im Ordner obj\\Debug erstellt.  
  
7.  Kopieren Sie die Datei LocalizingWpfInWf.resources.dll in den Ordner bin\\Debug\\es\-ES des Projekts.  Ersetzen Sie die vorhandene Datei.  
  
8.  Führen Sie die Datei LocalizingWpfInWf.exe aus, die sich im Ordner bin\\Debug des Projekts befindet.  Erstellen Sie die Anwendung nicht neu, da sonst die Satellitenassembly überschrieben wird.  
  
     Die Anwendung zeigt statt der englischen Zeichenfolgen die lokalisierten Zeichenfolgen an.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/de-de/9a96220d-a19b-4de0-9f48-01e5d82679e5)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)
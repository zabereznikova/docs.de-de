---
title: "&#220;bersicht &#252;ber die strukturierte Navigation | Microsoft Docs"
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
  - "Strukturierte Navigation [WPF]"
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
caps.latest.revision: 43
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# &#220;bersicht &#252;ber die strukturierte Navigation
Der von einer [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], einem <xref:System.Windows.Controls.Frame> oder einem <xref:System.Windows.Navigation.NavigationWindow> gehostete Inhalt besteht aus Seiten, die über die [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] des Pakets identifiziert und über Links aufgerufen werden.  Die Struktur der Seiten und die durch Links definierte Navigation in ihnen werden als Navigationstopologie bezeichnet.  Eine solche Topologie kann für unterschiedliche Anwendungstypen eingesetzt werden, insbesondere für die Navigation in Dokumenten.  In diesen Anwendungen kann der Benutzer von einer Seite zu einer anderen Seite navigieren, ohne dass die Seite Informationen zu der anderen Seite enthält.  
  
 In anderen Anwendungstypen ist es hingegen erforderlich, dass die Seiten Informationen über den Navigationsverlauf beinhalten.  Beispiel: Eine Personalanwendung enthält eine Seite, auf der alle Mitarbeiter eines Unternehmens aufgelistet sind \(die "Mitarbeiterliste"\).  Auf dieser Seite können Benutzer mithilfe eines Links einen neuen Mitarbeiter hinzufügen.  Wenn der Benutzer auf diesen Link klickt, navigiert die Seite zu der Seite "Mitarbeiter hinzufügen", auf der die Daten des neuen Mitarbeiters erfasst werden. Anschließend wird die Seite "Mitarbeiterliste" wieder aufgerufen, um den neuen Mitarbeiter zu erstellen und die Liste zu aktualisieren.  Diese Art der Navigation entspricht dem Aufruf einer Methode, um bestimmte Verarbeitungsschritte auszuführen und einen Wert zurückzugeben, was auch als strukturierte Programmierung bezeichnet wird.  Dementsprechend wird diese Art der Navigation als *strukturierte Navigation* bezeichnet.  
  
 Die <xref:System.Windows.Controls.Page>\-Klasse implementiert keine Unterstützung für die strukturierte Navigation.  Stattdessen wird die <xref:System.Windows.Navigation.PageFunction%601>\-Klasse von <xref:System.Windows.Controls.Page> abgeleitet und erweitert diese um die grundlegenden Konstrukte für die strukturierte Navigation.  In diesem Thema wird gezeigt, wie Sie mithilfe von <xref:System.Windows.Navigation.PageFunction%601> die strukturierte Navigation einrichten.  
  
   
  
<a name="Structured_Navigation"></a>   
## Strukturierte Navigation  
 Wenn eine Seite in einer strukturierten Navigation eine andere Seite aufruft, sind die folgenden Verhaltensweisen ganz oder teilweise erforderlich:  
  
-   Die aufrufende Seite navigiert zu der aufgerufenen Seite und übergibt ggf. für die aufgerufene Seite erforderliche Parameter.  
  
-   Die aufgerufene Seite kehrt zu der aufrufenden Seite zurück, wenn der Benutzer die Bearbeitung in der aufrufenden Seite abgeschlossen hat. Optional:  
  
    -   Es werden Zustandsinformationen zurückgegeben, die angeben, wie die aufrufende Seite beendet wurde \(z. B. ob der Benutzer auf die Schaltfläche OK oder Abbrechen geklickt hat\).  
  
    -   Die von dem Benutzer erfassten Daten werden zurückgegeben \(z. B. die Daten eines neuen Mitarbeiters\).  
  
-   Wenn die aufrufende Seite die aufgerufene Seite erneut anzeigt, wird die aufgerufene Seite aus dem Navigationsverlauf entfernt, um eine Instanz einer aufgerufenen Seite von einer anderen Instanz zu trennen.  
  
 Diese Verhaltensweisen werden in der folgenden Abbildung dargestellt.  
  
 ![Fluss zwischen aufrufender und aufgerufener Seite](../../../../docs/framework/wpf/app-development/media/structurednavigationoverviewfigure1.png "StructuredNavigationOverviewFigure1")  
  
 Sie implementieren diese Verhalten, indem Sie eine <xref:System.Windows.Navigation.PageFunction%601> als aufgerufene Seite verwenden.  
  
<a name="Structured_Navigation_with_PageFunction"></a>   
## Strukturierte Navigation mit PageFunction  
 In diesem Thema wird gezeigt, wie Sie die grundlegende Funktionsweise der strukturierten Navigation mit einer einzelnen <xref:System.Windows.Navigation.PageFunction%601> implementieren.  In diesem Beispiel ruft eine <xref:System.Windows.Controls.Page> eine <xref:System.Windows.Navigation.PageFunction%601> auf, um einen <xref:System.String>\-Wert vom Benutzer abzurufen und zurückzugeben.  
  
### Erstellen einer aufrufenden Seite  
 Die Seite, die eine <xref:System.Windows.Navigation.PageFunction%601> aufruft, kann eine <xref:System.Windows.Controls.Page> oder eine <xref:System.Windows.Navigation.PageFunction%601> sein.  In diesem Beispiel handelt es sich um eine <xref:System.Windows.Controls.Page>, wie dem folgenden Code zu entnehmen ist.  
  
 [!code-xml[StructuredNavigationSample#CallingPageDefaultMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]  
[!code-xml[StructuredNavigationSample#CallingPageDefaultMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]  
  
 [!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
 [!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]  
  
### Erstellen einer aufzurufenden Seitenfunktion  
 Da die aufrufende Seite mithilfe der aufgerufenen Seite Daten von dem Benutzer erfassen und zurückgeben kann, wird <xref:System.Windows.Navigation.PageFunction%601> als allgemeine Klasse implementiert, durch deren Typargument die Art des Werts angegeben wird, den die aufgerufene Seite zurückgibt.  Der folgende Code stellt die Anfangsimplementierung der aufgerufenen Seite dar. Es wird eine <xref:System.Windows.Navigation.PageFunction%601> verwendet, die eine <xref:System.String> zurückgibt.  
  
 [!code-xml[StructuredNavigationSample#CalledPageFunctionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]  
  
 [!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
 [!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]  
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]  
  
 Die Deklaration einer <xref:System.Windows.Navigation.PageFunction%601> ähnelt der Deklaration einer <xref:System.Windows.Controls.Page>, sie weist jedoch zusätzlich Typargumente auf.  Wie Sie dem Codebeispiel entnehmen können, werden die Typargumente sowohl im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup \(mithilfe des `x:TypeArguments`\-Attributs\), als auch im Code\-Behind \(mithilfe der standardmäßigen Syntax für allgemeine Typargumente\) angegeben.  
  
 Sie müssen nicht immer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Klassen als Typargumente verwenden.  Sie können eine <xref:System.Windows.Navigation.PageFunction%601> aufrufen, um domänenspezifische Daten zu erfassen, die als benutzerdefinierter Typ abstrahiert werden.  Im folgenden Code wird gezeigt, wie ein benutzerdefinierter Typ als Typargument für eine <xref:System.Windows.Navigation.PageFunction%601> verwendet wird.  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]  
  
 [!code-xml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]  
[!code-xml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]  
  
  
 Die Typargumente für die <xref:System.Windows.Navigation.PageFunction%601> sind die Grundlage für die Kommunikation zwischen einer aufrufenden Seite und einer aufgerufenen Seite, was in den folgenden Abschnitten näher erläutert wird.  
  
 Wie Sie sehen, hat der Typ, der durch die Deklaration einer <xref:System.Windows.Navigation.PageFunction%601> angegeben wird, eine wichtige Funktion beim Zurückgeben von Daten aus einer <xref:System.Windows.Navigation.PageFunction%601> an die aufrufende Seite.  
  
### Aufrufen einer PageFunction und Übergeben von Parametern  
 Um eine Seite aufzurufen, muss die aufrufende Seite die aufgerufene Seite instanzieren und mithilfe der <xref:System.Windows.Navigation.NavigationService.Navigate%2A>\-Methode zu dieser navigieren.  Die aufrufende Seite kann so erste Daten an die aufgerufene Seite übergeben, darunter Standardwerte für die von der aufgerufenen Seite erfassten Daten.  
  
 Im folgenden Code ist die aufgerufene Seite mit einem anderen als dem Standardkonstruktor dargestellt, um Parameter aus der aufrufenden Seite zu übernehmen.  
  
 [!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
 [!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]  
  
 Im folgenden Code ist die aufrufende Seite dargestellt, die das <xref:System.Windows.Documents.Hyperlink.Click>\-Ereignis des <xref:System.Windows.Documents.Hyperlink>\-Elements verarbeitet, um die aufgerufene Seite zu instanziieren und einen ersten Zeichenfolgenwert an diese zu übergeben.  
  
 [!code-xml[StructuredNavigationSample#PassingDataMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]  
  
 Es ist nicht erforderlich, Parameter an die aufgerufene Seite zu übergeben.  Sie können stattdessen auch die folgenden Schritte durchführen.  
  
-   Auf der aufrufenden Seite:  
  
    1.  Instanzieren Sie die aufgerufene <xref:System.Windows.Navigation.PageFunction%601> mit dem Standardkonstruktor.  
  
    2.  Speichern Sie die Parameter in <xref:System.Windows.Application.Properties%2A>.  
  
    3.  Navigieren Sie zu der aufgerufenen <xref:System.Windows.Navigation.PageFunction%601>.  
  
-   In der aufgerufenen <xref:System.Windows.Navigation.PageFunction%601>:  
  
    -   Rufen Sie die in <xref:System.Windows.Application.Properties%2A> gespeicherten Parameter ab, und verwenden Sie diese.  
  
 Sie müssen jedoch weiterhin Code verwenden, um die aufgerufene Seite zu instanzieren und zu dieser zu navigieren, sodass die von der aufgerufenen Seite zurückgegebenen Daten erfasst werden können \(siehe Beschreibung weiter unten\).  Die <xref:System.Windows.Navigation.PageFunction%601> muss daher weiterhin aktiv sein. Andernfalls würde [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die <xref:System.Windows.Navigation.PageFunction%601> mit dem Standardkonstruktor instanzieren, wenn Sie das nächste Mal zu der <xref:System.Windows.Navigation.PageFunction%601> navigieren.  
  
 Bevor die aufgerufene Seite wieder angezeigt werden kann, muss sie die Daten zurückgeben, die von der aufrufenden Seite abgerufen werden können.  
  
### Zurückgeben von Aufgabenergebnissen und Aufgabendaten aus einer Aufgabe an eine aufrufende Seite  
 Nachdem der Benutzer alle Aufgaben auf der aufgerufenen Seite beendet hat und wie in diesem Beispiel auf OK oder Abbrechen geklickt hat, muss die aufgerufene Seite wieder angezeigt werden.  Da die aufrufende Seite die aufgerufene Seite zum Erfassen von Daten des Benutzers verwendet hat, erfordert die aufrufende Seite zwei Arten von Informationen:  
  
1.  Ob der Benutzer die aufgerufene Seite abgebrochen hat \(indem er wie in diesem Beispiel auf OK oder Abbrechen geklickt hat\).  Die aufrufende Seite ermittelt anhand dieser Informationen, ob die von der aufrufenden Seite erfassten Daten des Benutzers verarbeitet werden sollen.  
  
2.  Die Daten, die vom Benutzer angegeben wurden.  
  
 Um Informationen zurückzugeben, implementiert <xref:System.Windows.Navigation.PageFunction%601> die <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>\-Methode.  Im folgenden Code wird veranschaulicht, wie diese aufgerufen wird.  
  
 [!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
 [!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]  
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]  
  
 Wenn der Benutzer in diesem Beispiel auf die Schaltfläche Abbrechen klickt, wird der Wert `null` an die aufrufende Seite zurückgegeben.  Wird stattdessen die Schaltfläche OK ausgewählt, wird der vom Benutzer angegebene Zeichenfolgenwert zurückgegeben.  <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> ist eine `protected` `virtual`\-Methode, die aufgerufen wird, um Daten an die aufrufende Seite zurückzugeben.  Die Daten müssen in einer Instanz des allgemeinen <xref:System.Windows.Navigation.ReturnEventArgs%601>\-Typs zusammengefasst werden, dessen Typargument die Art des Werts kennzeichnet, der von <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> zurückgegeben wird.  Wenn Sie eine <xref:System.Windows.Navigation.PageFunction%601> mit einem bestimmten Typargument deklarieren, geben Sie an, dass eine <xref:System.Windows.Navigation.PageFunction%601> eine Instanz des durch das Typargument definierten Typs zurückgibt.  In diesem Beispiel entsprechen das Typargument und infolgedessen der Rückgabewert dem Typ <xref:System.String>.  
  
 Wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, muss die aufrufende Seite den Rückgabewert der <xref:System.Windows.Navigation.PageFunction%601> empfangen können.  Aus diesem Grund implementiert <xref:System.Windows.Navigation.PageFunction%601> das <xref:System.Windows.Navigation.PageFunction%601.Return>\-Ereignis für die Verarbeitung durch die aufrufende Seite.  Wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, wird <xref:System.Windows.Navigation.PageFunction%601.Return> ausgelöst. Die aufrufende Seite kann sich so mit <xref:System.Windows.Navigation.PageFunction%601.Return> registrieren, um die Benachrichtigung zu empfangen.  
  
 [!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
 [!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]  
  
### Entfernen von Aufgabenseiten nach Abschluss einer Aufgabe  
 Wenn eine aufgerufene Seite wieder angezeigt wird und der Benutzer diese nicht abgebrochen hat, verarbeitet die aufrufende Seite die von dem Benutzer angegebenen und von der aufgerufenen Seite zurückgegebenen Daten.  Eine solche Datenerfassung erfolgt zumeist isoliert. Wenn die aufgerufene Seite wieder angezeigt wird, muss die aufrufende Seite eine neue aufrufende Seite erstellen und zu dieser navigieren, um weitere Daten zu erfassen.  
  
 Der Benutzer kann jedoch zu einer vorherigen Instanz der aufrufenden Seite zurück navigieren, sofern die aufgerufene Seite nicht aus [dem Journal](GTMT) entfernt wurde.  Ob eine <xref:System.Windows.Navigation.PageFunction%601> in [dem Journal](GTMT) beibehalten wird, wird durch die <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A>\-Eigenschaft festgelegt.  Standardmäßig wird eine Seitenfunktion automatisch entfernt, wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, da <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> auf `true` festgelegt ist.  Um eine Seitenfunktion im Navigationsverlauf beizubehalten, nachdem <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wurde, legen Sie <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> auf `false` fest.  
  
<a name="Other_Types_of_Structured_Navigation"></a>   
## Andere Arten der strukturierten Navigation  
 In diesem Thema wird die grundlegende Verwendung einer <xref:System.Windows.Navigation.PageFunction%601> veranschaulicht, um eine strukturierte Navigation mit Aufruf\/Rückgabe zu unterstützten.  Auf dieser Grundlage können Sie dann komplexere Typen der strukturierten Navigation erstellen.  
  
 In bestimmten Situationen benötigt eine aufrufende Seite beispielsweise mehrere Seiten, um genügend Daten zu einem Benutzer zu erfassen oder um eine Aufgabe auszuführen.  Die Verwendung mehrerer Seiten wird als "Assistent" bezeichnet.  
  
 In anderen Situationen weisen Anwendungen möglicherweise komplexe Navigationstopologien auf, für deren effektive Ausführung eine strukturierte Navigation erforderlich ist.  Weitere Informationen finden Sie unter [Übersicht über Navigationstopologien](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Navigation.PageFunction%601>   
 <xref:System.Windows.Navigation.NavigationService>   
 [Übersicht über Navigationstopologien](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)
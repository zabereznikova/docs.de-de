---
title: "Übersicht über die strukturierte Navigation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
caps.latest.revision: "43"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b241e9a2dbe84833f43dadb2e979e5ee079706a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="structured-navigation-overview"></a>Übersicht über die strukturierte Navigation
Inhalt, der von gehostet werden kann eine [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], eine <xref:System.Windows.Controls.Frame>, oder ein <xref:System.Windows.Navigation.NavigationWindow> setzt sich aus der Seiten, die vom Pack identifiziert werden können [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] und durch Links navigiert. Die Struktur der Seiten und die durch Links definierte Navigation in ihnen werden als Navigationstopologie bezeichnet. Eine solche Topologie kann für unterschiedliche Anwendungstypen eingesetzt werden, insbesondere für die Navigation in Dokumenten. In diesen Anwendungen kann der Benutzer von einer Seite zu einer anderen Seite navigieren, ohne dass die Seite Informationen zu der anderen Seite enthält.  
  
 In anderen Anwendungstypen ist es hingegen erforderlich, dass die Seiten Informationen über den Navigationsverlauf beinhalten. Beispiel: Eine Personalanwendung enthält eine Seite, auf der alle Mitarbeiter eines Unternehmens aufgelistet sind (die „Mitarbeiterliste“). Auf dieser Seite können Benutzer mithilfe eines Links einen neuen Mitarbeiter hinzufügen. Wenn der Benutzer auf diesen Link klickt, navigiert die Seite zu der Seite „Mitarbeiter hinzufügen“, auf der die Daten des neuen Mitarbeiters erfasst werden. Anschließend wird die Seite „Mitarbeiterliste“ wieder aufgerufen, um den neuen Mitarbeiter zu erstellen und die Liste zu aktualisieren. Diese Art der Navigation entspricht dem Aufruf einer Methode, um bestimmte Verarbeitungsschritte auszuführen und einen Wert zurückzugeben, was auch als strukturierte Programmierung bezeichnet wird. Dementsprechend wird diese Art der Navigation als *strukturierte Navigation* bezeichnet.  
  
 Die <xref:System.Windows.Controls.Page> Klasse implementiert keine Unterstützung für die strukturierte Navigation. Stattdessen die <xref:System.Windows.Navigation.PageFunction%601> Klasse leitet sich von <xref:System.Windows.Controls.Page> und erweitert sie mit der grundlegenden Konstrukte für die strukturierte Navigation. In diesem Thema wird gezeigt, wie mithilfe von strukturierten Navigation herstellen <xref:System.Windows.Navigation.PageFunction%601>.  
  
 
  
<a name="Structured_Navigation"></a>   
## <a name="structured-navigation"></a>Strukturierte Navigation  
 Wenn eine Seite in einer strukturierten Navigation eine andere Seite aufruft, sind die folgenden Verhaltensweisen ganz oder teilweise erforderlich:  
  
-   Die aufrufende Seite navigiert zu der aufgerufenen Seite und übergibt ggf. für die aufgerufene Seite erforderliche Parameter.  
  
-   Die aufgerufene Seite kehrt zu der aufrufenden Seite zurück, wenn der Benutzer die Bearbeitung in der aufrufenden Seite abgeschlossen hat. Optional:  
  
    -   Es werden Zustandsinformationen zurückgegeben, die angeben, wie die aufrufende Seite beendet wurde (z. B. ob der Benutzer auf die Schaltfläche „OK“ oder „Abbrechen“ geklickt hat).  
  
    -   Die von dem Benutzer erfassten Daten werden zurückgegeben (z. B. die Daten eines neuen Mitarbeiters).  
  
-   Wenn die aufrufende Seite die aufgerufene Seite erneut anzeigt, wird die aufgerufene Seite aus dem Navigationsverlauf entfernt, um eine Instanz einer aufgerufenen Seite von einer anderen Instanz zu trennen.  
  
 Diese Verhaltensweisen werden in der folgenden Abbildung dargestellt.  
  
 ![Fluss zwischen aufrufender und aufgerufener Seite](../../../../docs/framework/wpf/app-development/media/structurednavigationoverviewfigure1.png "StructuredNavigationOverviewFigure1")  
  
 Sie können dieses Verhalten implementieren, indem eine <xref:System.Windows.Navigation.PageFunction%601> als aufgerufene Seite.  
  
<a name="Structured_Navigation_with_PageFunction"></a>   
## <a name="structured-navigation-with-pagefunction"></a>Strukturierte Navigation mit PageFunction  
 In diesem Thema wird gezeigt, wie die grundlegende Funktionsweise der strukturierten Navigation mit einer einzelnen implementieren <xref:System.Windows.Navigation.PageFunction%601>. In diesem Beispiel wird eine <xref:System.Windows.Controls.Page> Aufrufe einer <xref:System.Windows.Navigation.PageFunction%601> zum Abrufen einer <xref:System.String> -Wert vom Benutzer erstellt und zurückgegeben.  
  
### <a name="creating-a-calling-page"></a>Erstellen einer aufrufenden Seite  
 Die Seite, die Aufrufe einer <xref:System.Windows.Navigation.PageFunction%601> kann es sich um eine <xref:System.Windows.Controls.Page> oder eine <xref:System.Windows.Navigation.PageFunction%601>. In diesem Beispiel ist dies ein <xref:System.Windows.Controls.Page>, wie im folgenden Code gezeigt.  
  
 [!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]  
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]  
  
 [!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
 [!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]  
  
### <a name="creating-a-page-function-to-call"></a>Erstellen einer aufzurufenden Seitenfunktion  
 Da die aufrufende Seite die aufgerufene Seite verwenden kann, zu erfassen und Zurückgeben von Daten aus der Benutzer <xref:System.Windows.Navigation.PageFunction%601> wird implementiert, wie eine generische Klasse, deren Typargument gibt den Typ des Werts, der die aufgerufene Seite zurückgegeben wird. Der folgende Code zeigt die erste Implementierung der aufgerufenen Seite mit einem <xref:System.Windows.Navigation.PageFunction%601>, welche gibt eine <xref:System.String>.  
  
 [!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]  
  
 [!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
 [!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]  
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]  
  
 Die Deklaration einer <xref:System.Windows.Navigation.PageFunction%601> ähnelt der Deklaration des eine <xref:System.Windows.Controls.Page> durch das Hinzufügen von Typargumenten. Wie Sie dem Codebeispiel entnehmen können, werden die Typargumente sowohl im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup (mithilfe des `x:TypeArguments`-Attributs), als auch im Code-Behind (mithilfe der standardmäßigen Syntax für allgemeine Typargumente) angegeben.  
  
 Sie müssen nicht immer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Klassen als Typargumente verwenden. Ein <xref:System.Windows.Navigation.PageFunction%601> kann aufgerufen werden, um domänenspezifische Daten zu erfassen, die als benutzerdefinierter Typ abstrahiert wird. Der folgende Code zeigt, wie Sie einen benutzerdefinierten Typ als Typargument für eine <xref:System.Windows.Navigation.PageFunction%601>.  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]  
  
 [!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]  
[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind2)]  
  
 Die Typargumente für die <xref:System.Windows.Navigation.PageFunction%601> bilden die Grundlage für die Kommunikation zwischen einer aufrufenden und der aufgerufener Seite, die in den folgenden Abschnitten erläutert werden.  
  
 Wie Sie sehen, den Typ, der durch die Deklaration von identifiziert wird eine <xref:System.Windows.Navigation.PageFunction%601> spielt eine wichtige Rolle beim Zurückgeben von Daten aus einer <xref:System.Windows.Navigation.PageFunction%601> an die aufrufende Seite.  
  
### <a name="calling-a-pagefunction-and-passing-parameters"></a>Aufrufen einer PageFunction und Übergeben von Parametern  
 Rufen Sie eine Seite auf die aufrufende Seite instanziieren die aufgerufene Seite muss, und navigieren Sie mithilfe der <xref:System.Windows.Navigation.NavigationService.Navigate%2A> Methode. Die aufrufende Seite kann so erste Daten an die aufgerufene Seite übergeben, darunter Standardwerte für die von der aufgerufenen Seite erfassten Daten.  
  
 Im folgenden Code ist die aufgerufene Seite mit einem anderen als dem Standardkonstruktor dargestellt, um Parameter aus der aufrufenden Seite zu übernehmen.  
  
 [!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
 [!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]  
  
 Der folgende Code zeigt die aufrufende Seite Behandlung der <xref:System.Windows.Documents.Hyperlink.Click> -Ereignis für die <xref:System.Windows.Documents.Hyperlink> zum Instanziieren von der aufgerufenen Seite und einen Zeichenfolgenwert für die erste zu übergeben.  
  
 [!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]  
  
 Es ist nicht erforderlich, Parameter an die aufgerufene Seite zu übergeben. Sie können stattdessen auch die folgenden Schritte durchführen.  
  
-   Auf der aufrufenden Seite:  
  
    1.  Die aufgerufene instanziieren <xref:System.Windows.Navigation.PageFunction%601> mit dem Standardkonstruktor.  
  
    2.  Speichern Sie die Parameter in <xref:System.Windows.Application.Properties%2A>.  
  
    3.  Navigieren Sie zu die aufgerufene <xref:System.Windows.Navigation.PageFunction%601>.  
  
-   In der aufgerufenen <xref:System.Windows.Navigation.PageFunction%601>:  
  
    -   Abrufen und verwenden Sie die Parameter in gespeicherten <xref:System.Windows.Application.Properties%2A>.  
  
 Sie müssen jedoch weiterhin Code verwenden, um die aufgerufene Seite zu instanzieren und zu dieser zu navigieren, sodass die von der aufgerufenen Seite zurückgegebenen Daten erfasst werden können (siehe Beschreibung weiter unten). Aus diesem Grund die <xref:System.Windows.Navigation.PageFunction%601> Anforderungen entsprochen werden kann, andernfalls erhalten, das nächste Mal navigieren Sie zu der <xref:System.Windows.Navigation.PageFunction%601>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] instanziiert die <xref:System.Windows.Navigation.PageFunction%601> mit dem Standardkonstruktor.  
  
 Bevor die aufgerufene Seite wieder angezeigt werden kann, muss sie die Daten zurückgeben, die von der aufrufenden Seite abgerufen werden können.  
  
### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>Zurückgeben von Aufgabenergebnissen und Aufgabendaten aus einer Aufgabe an eine aufrufende Seite  
 Nachdem der Benutzer alle Aufgaben auf der aufgerufenen Seite beendet hat und wie in diesem Beispiel auf „OK“ oder „Abbrechen“ geklickt hat, muss die aufgerufene Seite wieder angezeigt werden. Da die aufrufende Seite die aufgerufene Seite dazu verwendet hat, um Daten vom Benutzer zu erfassen, benötigt die aufrufende Seite zwei Arten von Informationen:  
  
1.  Ob der Benutzer die aufgerufene Seite abgebrochen hat (indem er wie in diesem Beispiel auf „OK“ oder „Abbrechen“ geklickt hat). Die aufrufende Seite ermittelt anhand dieser Informationen, ob die von der aufrufenden Seite erfassten Daten des Benutzers verarbeitet werden sollen.  
  
2.  Die Daten, die vom Benutzer angegeben wurden.  
  
 Um Informationen zurückzugeben <xref:System.Windows.Navigation.PageFunction%601> implementiert die <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> Methode. Im folgenden Code wird veranschaulicht, wie diese aufgerufen wird.  
  
 [!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
 [!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]  
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]  
  
 Wenn der Benutzer in diesem Beispiel auf die Schaltfläche „Abbrechen“ klickt, wird der Wert `null` an die aufrufende Seite zurückgegeben. Wird stattdessen die Schaltfläche „OK“ ausgewählt, wird der vom Benutzer angegebene Zeichenfolgenwert zurückgegeben. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>ist eine `protected``virtual` Methode, die Sie aufrufen, um Ihre Daten an die aufrufende Seite zurück. Ihre Daten müssen in einer Instanz der generischen verpackt werden <xref:System.Windows.Navigation.ReturnEventArgs%601> Typ, dessen Type-Argument gibt den Typ der Wert <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> zurückgegeben. Auf diese Weise beim Deklarieren einer <xref:System.Windows.Navigation.PageFunction%601> mit einem bestimmten Typ-Argument, werden Sie besagt, dass eine <xref:System.Windows.Navigation.PageFunction%601> wird eine Instanz des Typs, der durch das Typargument angegeben wird zurückgegeben. In diesem Beispiel wird das Typargument und folglich auch der Rückgabewert ist vom Typ <xref:System.String>.  
  
 Wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wurde, muss die aufrufende Seite Weise empfängt den Rückgabewert der <xref:System.Windows.Navigation.PageFunction%601>. Aus diesem Grund <xref:System.Windows.Navigation.PageFunction%601> implementiert die <xref:System.Windows.Navigation.PageFunction%601.Return> Ereignis zum Aufrufen von Seiten zu behandeln. Wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, <xref:System.Windows.Navigation.PageFunction%601.Return> ausgelöst wird, damit die aufrufende Seite mit registrieren kann <xref:System.Windows.Navigation.PageFunction%601.Return> die benachrichtigt werden soll.  
  
 [!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
 [!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]  
  
### <a name="removing-task-pages-when-a-task-completes"></a>Entfernen von Aufgabenseiten nach Abschluss einer Aufgabe  
 Wenn eine aufgerufene Seite wieder angezeigt wird und der Benutzer diese nicht abgebrochen hat, verarbeitet die aufrufende Seite die von dem Benutzer angegebenen und von der aufgerufenen Seite zurückgegebenen Daten. Eine solche Datenerfassung erfolgt zumeist isoliert. Wenn die aufgerufene Seite wieder angezeigt wird, muss die aufrufende Seite eine neue aufrufende Seite erstellen und zu dieser navigieren, um weitere Daten zu erfassen.  
  
 Der Benutzer kann jedoch zu einer vorherigen Instanz der aufrufenden Seite zurück navigieren, sofern die aufgerufene Seite nicht aus dem Journal entfernt wurde. Ob eine <xref:System.Windows.Navigation.PageFunction%601> bleiben in die Erfassung richtet sich nach der <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> Eigenschaft. Standardmäßig wird eine Seitenfunktion automatisch entfernt wird, wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> wird aufgerufen, da <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> festgelegt ist, um `true`. Eine Seitenfunktion im Navigationsverlauf nach beibehalten <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, legen Sie <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> auf `false`.  
  
<a name="Other_Types_of_Structured_Navigation"></a>   
## <a name="other-types-of-structured-navigation"></a>Andere Arten der strukturierten Navigation  
 Dieses Thema veranschaulicht die grundlegende Verwendung von einem <xref:System.Windows.Navigation.PageFunction%601> Aufruf/Rückgabe unterstützt strukturierte Navigation. Auf dieser Grundlage können Sie dann komplexere Typen der strukturierten Navigation erstellen.  
  
 In bestimmten Situationen benötigt eine aufrufende Seite beispielsweise mehrere Seiten, um genügend Daten zu einem Benutzer zu erfassen oder um eine Aufgabe auszuführen. Die Verwendung mehrerer Seiten wird als „Assistent“ bezeichnet.  
  
 In anderen Situationen weisen Anwendungen möglicherweise komplexe Navigationstopologien auf, für deren effektive Ausführung eine strukturierte Navigation erforderlich ist. Weitere Informationen finden Sie unter [Übersicht über Navigationstopologien](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Navigation.PageFunction%601>  
 <xref:System.Windows.Navigation.NavigationService>  
 [Übersicht über Navigationstopologien](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)

---
title: Übersicht über die strukturierte Navigation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: 09c3c57f3ac1009416a5c67b37c035fe30cd5b5e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425328"
---
# <a name="structured-navigation-overview"></a>Übersicht über die strukturierte Navigation

Inhalte, die von einer XAML-Browser Anwendung (XBAP), einer <xref:System.Windows.Controls.Frame>oder einer <xref:System.Windows.Navigation.NavigationWindow> gehostet werden können, bestehen aus Seiten, die durch die Paket-Uniform Resource Identifier (URIs) identifiziert und durch Hyperlinks navigiert werden können. Die Struktur der Seiten und die durch Links definierte Navigation in ihnen werden als Navigationstopologie bezeichnet. Eine solche Topologie kann für unterschiedliche Anwendungstypen eingesetzt werden, insbesondere für die Navigation in Dokumenten. In diesen Anwendungen kann der Benutzer von einer Seite zu einer anderen Seite navigieren, ohne dass die Seite Informationen zu der anderen Seite enthält.

In anderen Anwendungstypen ist es hingegen erforderlich, dass die Seiten Informationen über den Navigationsverlauf beinhalten. Beispiel: Eine Personalanwendung enthält eine Seite, auf der alle Mitarbeiter eines Unternehmens aufgelistet sind (die „Mitarbeiterliste“). Auf dieser Seite können Benutzer mithilfe eines Links einen neuen Mitarbeiter hinzufügen. Wenn der Benutzer auf diesen Link klickt, navigiert die Seite zu der Seite „Mitarbeiter hinzufügen“, auf der die Daten des neuen Mitarbeiters erfasst werden. Anschließend wird die Seite „Mitarbeiterliste“ wieder aufgerufen, um den neuen Mitarbeiter zu erstellen und die Liste zu aktualisieren. Diese Art der Navigation entspricht dem Aufruf einer Methode, um bestimmte Verarbeitungsschritte auszuführen und einen Wert zurückzugeben, was auch als strukturierte Programmierung bezeichnet wird. Dementsprechend wird diese Art der Navigation als *strukturierte Navigation* bezeichnet.

Die <xref:System.Windows.Controls.Page>-Klasse implementiert nicht die Unterstützung für die strukturierte Navigation. Stattdessen wird die <xref:System.Windows.Navigation.PageFunction%601>-Klasse von <xref:System.Windows.Controls.Page> abgeleitet und durch die grundlegenden Konstrukte erweitert, die für die strukturierte Navigation erforderlich sind. In diesem Thema wird gezeigt, wie Sie eine strukturierte Navigation mit <xref:System.Windows.Navigation.PageFunction%601>einrichten.

<a name="Structured_Navigation"></a>

## <a name="structured-navigation"></a>Strukturierte Navigation

Wenn eine Seite in einer strukturierten Navigation eine andere Seite aufruft, sind die folgenden Verhaltensweisen ganz oder teilweise erforderlich:

- Die aufrufende Seite navigiert zu der aufgerufenen Seite und übergibt ggf. für die aufgerufene Seite erforderliche Parameter.

- Die aufgerufene Seite kehrt zu der aufrufenden Seite zurück, wenn der Benutzer die Bearbeitung in der aufrufenden Seite abgeschlossen hat. Optional:

  - Es werden Zustandsinformationen zurückgegeben, die angeben, wie die aufrufende Seite beendet wurde (z. B. ob der Benutzer auf die Schaltfläche „OK“ oder „Abbrechen“ geklickt hat).

  - Die von dem Benutzer erfassten Daten werden zurückgegeben (z. B. die Daten eines neuen Mitarbeiters).

- Wenn die aufrufende Seite die aufgerufene Seite erneut anzeigt, wird die aufgerufene Seite aus dem Navigationsverlauf entfernt, um eine Instanz einer aufgerufenen Seite von einer anderen Instanz zu trennen.

Diese Verhaltensweisen werden in der folgenden Abbildung veranschaulicht:

![Screenshot zeigt den Flow zwischen der aufrufenden Seite und der aufgerufenen Seite an.](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)

Sie können diese Verhaltensweisen implementieren, indem Sie eine <xref:System.Windows.Navigation.PageFunction%601> als aufgerufene Seite verwenden.

<a name="Structured_Navigation_with_PageFunction"></a>

## <a name="structured-navigation-with-pagefunction"></a>Strukturierte Navigation mit PageFunction

In diesem Thema wird gezeigt, wie die grundlegende Mechanik der strukturierten Navigation mit einem einzelnen <xref:System.Windows.Navigation.PageFunction%601>implementiert wird. In diesem Beispiel ruft ein <xref:System.Windows.Controls.Page> eine <xref:System.Windows.Navigation.PageFunction%601> auf, um einen <xref:System.String> Wert vom Benutzer zu erhalten und zurückzugeben.

### <a name="creating-a-calling-page"></a>Erstellen einer aufrufenden Seite

Die Seite, die einen <xref:System.Windows.Navigation.PageFunction%601> aufruft, kann entweder ein <xref:System.Windows.Controls.Page> oder ein <xref:System.Windows.Navigation.PageFunction%601>sein. In diesem Beispiel handelt es sich um eine <xref:System.Windows.Controls.Page>, wie im folgenden Code dargestellt.

[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]

[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]

### <a name="creating-a-page-function-to-call"></a>Erstellen einer aufzurufenden Seitenfunktion

Da die aufrufende Seite die aufgerufene Seite zum Erfassen und Zurückgeben von Daten vom Benutzer verwenden kann, wird <xref:System.Windows.Navigation.PageFunction%601> als generische Klasse implementiert, deren Typargument den Typ des Werts angibt, der von der aufgerufenen Seite zurückgegeben wird. Der folgende Code zeigt die anfängliche Implementierung der aufgerufenen Seite unter Verwendung einer <xref:System.Windows.Navigation.PageFunction%601>, die eine <xref:System.String>zurückgibt.

[!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]

[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]

Die Deklaration einer <xref:System.Windows.Navigation.PageFunction%601> ähnelt der Deklaration einer <xref:System.Windows.Controls.Page> mit dem Hinzufügen der Typargumente. Wie Sie dem Codebeispiel entnehmen können, werden die Typargumente sowohl im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup (mithilfe des `x:TypeArguments`-Attributs), als auch im Code-Behind (mithilfe der standardmäßigen Syntax für allgemeine Typargumente) angegeben.

Sie müssen nicht nur .NET Framework-Klassen als Typargumente verwenden. Eine <xref:System.Windows.Navigation.PageFunction%601> könnte aufgerufen werden, um domänenspezifische Daten zu erfassen, die als benutzerdefinierter Typ abstrahiert werden. Der folgende Code zeigt, wie Sie einen benutzerdefinierten Typ als Typargument für eine <xref:System.Windows.Navigation.PageFunction%601>verwenden.

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]

[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]
[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind2)]

Die Typargumente für den <xref:System.Windows.Navigation.PageFunction%601> bilden die Grundlage für die Kommunikation zwischen einer aufrufenden Seite und der aufgerufenen Seite, die in den folgenden Abschnitten erläutert werden.

Wie Sie sehen werden, spielt der Typ, der mit der Deklaration einer <xref:System.Windows.Navigation.PageFunction%601> identifiziert wird, eine wichtige Rolle beim Zurückgeben von Daten aus einem <xref:System.Windows.Navigation.PageFunction%601> an die aufrufende Seite.

### <a name="calling-a-pagefunction-and-passing-parameters"></a>Aufrufen einer PageFunction und Übergeben von Parametern

Um eine Seite aufzurufen, muss die aufrufende Seite die aufgerufene Seite instanziieren und mithilfe der <xref:System.Windows.Navigation.NavigationService.Navigate%2A>-Methode dorthin navigieren. Die aufrufende Seite kann so erste Daten an die aufgerufene Seite übergeben, darunter Standardwerte für die von der aufgerufenen Seite erfassten Daten.

Der folgende Code zeigt die aufgerufene Seite mit einem nicht Parameter losen Konstruktor, um Parameter von der aufrufenden Seite zu akzeptieren.

[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]

Der folgende Code zeigt die aufrufende Seite, die das <xref:System.Windows.Documents.Hyperlink.Click>-Ereignis der <xref:System.Windows.Documents.Hyperlink> behandelt, um die aufgerufene Seite zu instanziieren und ihr einen anfänglichen Zeichen folgen Wert zu übergeben.

[!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]

Es ist nicht erforderlich, Parameter an die aufgerufene Seite zu übergeben. Sie können stattdessen auch die folgenden Schritte durchführen.

- Auf der aufrufenden Seite:

  1. Instanziieren Sie das aufgerufene <xref:System.Windows.Navigation.PageFunction%601> mit dem Parameter losen Konstruktor.

  2. Speichern Sie die Parameter in <xref:System.Windows.Application.Properties%2A>.

  3. Navigieren Sie zum aufgerufenen <xref:System.Windows.Navigation.PageFunction%601>.

- Aus dem aufgerufenen <xref:System.Windows.Navigation.PageFunction%601>:

  - Rufen Sie die in <xref:System.Windows.Application.Properties%2A>gespeicherten Parameter ab, und verwenden Sie Sie.

Sie müssen jedoch weiterhin Code verwenden, um die aufgerufene Seite zu instanzieren und zu dieser zu navigieren, sodass die von der aufgerufenen Seite zurückgegebenen Daten erfasst werden können (siehe Beschreibung weiter unten). Aus diesem Grund muss die <xref:System.Windows.Navigation.PageFunction%601> aufrechterhalten werden. Andernfalls wird bei der nächsten Navigation zum <xref:System.Windows.Navigation.PageFunction%601>[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die <xref:System.Windows.Navigation.PageFunction%601> mit dem Parameter losen Konstruktor instanziiert.

Bevor die aufgerufene Seite wieder angezeigt werden kann, muss sie die Daten zurückgeben, die von der aufrufenden Seite abgerufen werden können.

### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>Zurückgeben von Aufgabenergebnissen und Aufgabendaten aus einer Aufgabe an eine aufrufende Seite

Nachdem der Benutzer alle Aufgaben auf der aufgerufenen Seite beendet hat und wie in diesem Beispiel auf „OK“ oder „Abbrechen“ geklickt hat, muss die aufgerufene Seite wieder angezeigt werden. Da die aufrufende Seite die aufgerufene Seite dazu verwendet hat, um Daten vom Benutzer zu erfassen, benötigt die aufrufende Seite zwei Arten von Informationen:

1. Ob der Benutzer die aufgerufene Seite abgebrochen hat (indem er wie in diesem Beispiel auf „OK“ oder „Abbrechen“ geklickt hat). Die aufrufende Seite ermittelt anhand dieser Informationen, ob die von der aufrufenden Seite erfassten Daten des Benutzers verarbeitet werden sollen.

2. Die Daten, die vom Benutzer angegeben wurden.

<xref:System.Windows.Navigation.PageFunction%601> implementiert die <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>-Methode, um Informationen zurückzugeben. Im folgenden Code wird veranschaulicht, wie diese aufgerufen wird.

[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]

Wenn der Benutzer in diesem Beispiel auf die Schaltfläche „Abbrechen“ klickt, wird der Wert `null` an die aufrufende Seite zurückgegeben. Wird stattdessen die Schaltfläche „OK“ ausgewählt, wird der vom Benutzer angegebene Zeichenfolgenwert zurückgegeben. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> ist eine `protected virtual` Methode, die Sie aufrufen, um die Daten an die aufrufende Seite zurückzugeben. Ihre Daten müssen in eine Instanz des generischen <xref:System.Windows.Navigation.ReturnEventArgs%601> Typs gepackt werden, deren Typargument den Typ des Werts angibt, den <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> zurückgibt. Wenn Sie auf diese Weise eine <xref:System.Windows.Navigation.PageFunction%601> mit einem bestimmten Typargument deklarieren, geben Sie an, dass eine <xref:System.Windows.Navigation.PageFunction%601> eine Instanz des Typs zurückgibt, der durch das Typargument angegeben wird. In diesem Beispiel ist das Typargument und folglich der Rückgabewert vom Typ <xref:System.String>.

Wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, benötigt die aufrufenden Seite eine Methode zum Empfangen des Rückgabewerts des <xref:System.Windows.Navigation.PageFunction%601>. Aus diesem Grund implementiert <xref:System.Windows.Navigation.PageFunction%601> das <xref:System.Windows.Navigation.PageFunction%601.Return>-Ereignis für das Aufrufen von Seiten, die behandelt werden sollen. Wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, wird <xref:System.Windows.Navigation.PageFunction%601.Return> ausgelöst, sodass die aufrufenden Seite bei <xref:System.Windows.Navigation.PageFunction%601.Return> registriert werden kann, um die Benachrichtigung zu empfangen.

[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]

### <a name="removing-task-pages-when-a-task-completes"></a>Entfernen von Aufgabenseiten nach Abschluss einer Aufgabe

Wenn eine aufgerufene Seite wieder angezeigt wird und der Benutzer diese nicht abgebrochen hat, verarbeitet die aufrufende Seite die von dem Benutzer angegebenen und von der aufgerufenen Seite zurückgegebenen Daten. Eine solche Datenerfassung erfolgt zumeist isoliert. Wenn die aufgerufene Seite wieder angezeigt wird, muss die aufrufende Seite eine neue aufrufende Seite erstellen und zu dieser navigieren, um weitere Daten zu erfassen.

Der Benutzer kann jedoch zu einer vorherigen Instanz der aufrufenden Seite zurück navigieren, sofern die aufgerufene Seite nicht aus dem Journal entfernt wurde. Ob ein <xref:System.Windows.Navigation.PageFunction%601> im Journal beibehalten wird, hängt von der <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A>-Eigenschaft ab. Standardmäßig wird eine Seiten Funktion automatisch entfernt, wenn <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wird, da <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> auf `true`festgelegt ist. Wenn eine Seiten Funktion im Navigationsverlauf beibehalten werden soll, nachdem <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> aufgerufen wurde, legen Sie <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> auf `false`fest.

<a name="Other_Types_of_Structured_Navigation"></a>

## <a name="other-types-of-structured-navigation"></a>Andere Arten der strukturierten Navigation

In diesem Thema wird die grundlegende Verwendung eines <xref:System.Windows.Navigation.PageFunction%601> zur Unterstützung der strukturierten Navigation für Aufrufe/Rückgabe veranschaulicht. Auf dieser Grundlage können Sie dann komplexere Typen der strukturierten Navigation erstellen.

In bestimmten Situationen benötigt eine aufrufende Seite beispielsweise mehrere Seiten, um genügend Daten zu einem Benutzer zu erfassen oder um eine Aufgabe auszuführen. Die Verwendung mehrerer Seiten wird als „Assistent“ bezeichnet.

In anderen Situationen weisen Anwendungen möglicherweise komplexe Navigationstopologien auf, für deren effektive Ausführung eine strukturierte Navigation erforderlich ist. Weitere Informationen finden Sie unter [Übersicht über Navigationstopologien](navigation-topologies-overview.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [Übersicht über Navigationstopologien](navigation-topologies-overview.md)

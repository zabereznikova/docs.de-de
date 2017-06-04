---
title: ".NET Framework-Unterst&#252;tzung f&#252;r Windows Store-Apps und Windows-Runtime | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Windows Store-Apps, .NET Framework-Unterstützung für"
  - "Windows-Runtime, .NET Framework-Unterstützung für"
  - ".NET für Windows Store-Apps"
  - ".NET Framework und Windows Store-Apps"
  - ".NET Framework und Windows-Runtime"
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 20
---
# .NET Framework-Unterst&#252;tzung f&#252;r Windows Store-Apps und Windows-Runtime
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] unterstützt mehrere Softwareentwicklungsszenarien mit [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Diese Szenarien werden in drei Kategorien eingeteilt:  
  
-   Entwickeln von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -apps mit XAML-Steuerelemente, wie in beschrieben [Roadmap für Windows Store-apps mit c# oder Visual Basic](http://go.microsoft.com/fwlink/p/?LinkID=242212), [Entwickeln von Windows Store-apps (VB / C#-/ C++ und XAML)](http://go.microsoft.com/fwlink/p/?LinkId=238311), und [.NET für Windows Store-apps – Übersicht](http://go.microsoft.com/fwlink/p/?LinkId=238312) im Windows Developer Center.  
  
-   Entwickeln von Klassenbibliotheken zur Verwendung in den [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps, die mit .NET Framework erstellt werden  
  
-   Entwickeln von [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten, verpackt in WinMD-Dateien, die von jeder Programmiersprache verwendet werden können, die [!INCLUDE[wrt](../../../includes/wrt-md.md)] unterstützt. Beispielsweise finden Sie unter [Erstellen von Windows-Runtime-Komponenten in c# und Visual Basic](http://go.microsoft.com/fwlink/p/?LinkId=238313) im Windows Developer Center.  
  
 In diesem Thema werden die Unterstützung, die .NET Framework für alle drei Kategorien bietet, sowie die Szenarien für [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten beschrieben. Der erste Abschnitt enthält grundlegende Informationen über die Beziehung zwischen .NET Framework und [!INCLUDE[wrt](../../../includes/wrt-md.md)] und erläutert einige Eigentümlichkeiten, die möglicherweise im Hilfesystem und in der IDE auftreten. Die [zweiter Abschnitt](#WindowsRuntimeComponents) erläutert Szenarien für die Entwicklung von [!INCLUDE[wrt](../../../includes/wrt-md.md)] Komponenten.  
  
## <a name="the-basics"></a>Die Grundlagen  
 .NET Framework unterstützt die drei zuvor aufgelisteten Entwicklungsszenarien durch die Bereitstellung von [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] und durch die Unterstützung von [!INCLUDE[wrt](../../../includes/wrt-md.md)].  
  
-   [.NET für Windows Store-apps](http://go.microsoft.com/fwlink/p/?LinkId=247912) bietet eine komprimierte Übersicht über die .NET Framework-Klassenbibliotheken und enthalten nur die Typen und Member Sie erstellen können [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps und [!INCLUDE[wrt](../../../includes/wrt-md.md)] Komponenten.  
  
    -   Wenn Sie Visual Studio ([!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] oder eine neuere Version) zum Entwickeln einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App oder einer [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente verwenden, stellt ein Satz von Verweisassemblys sicher, dass Sie nur die relevanten Typen und Member sehen.  
  
    -   Dieser gestraffte API-Satz wurde weiter vereinfacht, indem Funktionen entfernt wurden, die in .NET Framework doppelt vorhanden sind oder [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Funktionen duplizieren. Beispielsweise enthält er nur die generischen Versionen von Auflistungstypen, und das XML-Dokumentobjektmodell wurde zugunsten des [!INCLUDE[wrt](../../../includes/wrt-md.md)]-XML-API-Satzes entfernt.  
  
    -   Funktionen, die lediglich die Betriebssystem-API umschließen, wurden ebenfalls entfernt, da [!INCLUDE[wrt](../../../includes/wrt-md.md)] auf einfache Weise von verwaltetem Code aus aufgerufen werden kann.  
  
     Weitere Informationen die [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], finden Sie unter der [.NET für Windows Store-apps – Übersicht](http://go.microsoft.com/fwlink/p/?LinkId=238312) in der Windows Dev Center.To erfahren Sie mehr über die API-Auswahlverfahren, finden Sie unter der [.NET für Windows Store-apps](http://go.microsoft.com/fwlink/p/?LinkId=251061) Eintrag im .NET-Blog.  
  
-   Die [Windows-Runtime](http://go.microsoft.com/fwlink/p/?LinkId=238319) bietet dem Benutzer Elemente der Benutzeroberfläche für das Erstellen von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -apps und bietet Zugriff auf Funktionen des Betriebssystems. Wie .NET Framework verfügt [!INCLUDE[wrt](../../../includes/wrt-md.md)] über Metadaten, die es dem C#- und dem Visual Basic-Compiler ermöglichen, [!INCLUDE[wrt](../../../includes/wrt-md.md)] so zu verwenden, wie sie die .NET Framework-Klassenbibliotheken verwenden. .NET Framework vereinfacht die Verwendung von [!INCLUDE[wrt](../../../includes/wrt-md.md)] durch das Ausblenden einiger Unterschiede:  
  
    -   Einige Unterschiede bei Programmiermustern zwischen .NET Framework und [!INCLUDE[wrt](../../../includes/wrt-md.md)], beispielsweise das Muster für das Hinzufügen und Entfernen von Ereignishandlern, werden ausgeblendet. Sie verwenden einfach das .NET Framework-Muster.  
  
    -   Einige Unterschiede bei häufig verwendeten Typen (beispielsweise primitive Typen und Auflistungen) werden ausgeblendet. Sie verwenden einfach die .NET Framework-Typ wie in erläutert [Unterschiede, die angezeigt werden in der IDE](#DifferencesVisibleInIDE)weiter unten in diesem Artikel.  
  
 Meistens ist die .NET Framework-Unterstützung für [!INCLUDE[wrt](../../../includes/wrt-md.md)] transparent. Im nächsten Abschnitt werden einige offensichtliche Unterschiede zwischen verwaltetem Code und [!INCLUDE[wrt](../../../includes/wrt-md.md)] erläutert.  
  
<a name="AboutReferenceDocumentation"></a>   
### <a name="the-net-framework-and-the-includewrttokenwrtmdmd-reference-documentation"></a>Referenzdokumentation zu .NET Framework und [!INCLUDE[wrt](../../../includes/wrt-md.md)]  
 Windows und .NET Framework verfügen über separate Dokumentationssätze. Wenn Sie F1 drücken, um die Hilfe zu einem Typ oder einem Member aufzurufen, wird die Referenzdokumentation des entsprechenden Satzes angezeigt. Jedoch wenn Sie Durchsuchen der [Windows-Runtime-Referenz](http://go.microsoft.com/fwlink/p/?LinkId=238319) Beispiele, in denen verwirrende können auftreten:  
  
-   Themen wie die [IIterable-Schnittstelle](http://go.microsoft.com/fwlink/p/?LinkId=238321) weisen keine Deklarationssyntax für Visual Basic oder c#. Stattdessen wird ein Hinweis angezeigt, über dem Syntaxabschnitt (in diesem Fall ".NET: Diese Schnittstelle wird als System.Collections.Generic.IEnumerable<>\>"). Der Grund dafür besteht darin, dass .NET Framework und [!INCLUDE[wrt](../../../includes/wrt-md.md)] ähnliche Funktionen mit verschiedenen Schnittstellen bereitstellen. Darüber hinaus gibt es Verhaltensunterschiede: `IIterable` hat ein `First` -Methode anstelle einer <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Methode zum Zurückgeben des Enumerators. Anstatt Sie zu zwingen, eine andere Art der Ausführung einer häufig vorkommenden Aufgabe zu erlernen, unterstützt .NET Framework [!INCLUDE[wrt](../../../includes/wrt-md.md)], indem verwalteter Code scheinbar den Typ verwendet, mit dem Sie bereits vertraut sind. Sie sehen die `IIterable`-Schnittstelle in der IDE nicht. Daher bemerken Sie sie in der [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Referenzdokumentation nur, wenn Sie diese Dokumentation direkt durchsuchen.  
  
-   Die [SyndicationFeed-Konstruktor](http://go.microsoft.com/fwlink/p/?LinkId=238322) Dokumentation veranschaulicht ein eng verwandtes Problem: die Parametertypen scheinen für verschiedene Sprachen unterschiedlich sein. Für c# und Visual Basic sind die Parametertypen <xref:System.String?displayProperty=fullName> und <xref:System.Uri?displayProperty=fullName>. Auch hier besteht der Grund dafür darin, dass .NET Framework über eigene `String`- und `Uri`-Typen verfügt, und bei solchen häufig verwendeten Typen ist es nicht sinnvoll, .NET Framework-Benutzer zu zwingen, eine andere Art der Ausführung zu erlernen. In der IDE blendet .NET Framework die entsprechenden [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen aus.  
  
-   In einigen Fällen z. B. die [Windows.UI.Xaml.GridLength](http://go.microsoft.com/fwlink/p/?LinkId=251059) -Struktur, die .NET Framework bietet einen Typ mit demselben Namen, aber mehr Funktionalität. Beispielsweise ist `GridLength` eine Gruppe von Konstruktor- und Eigenschaftsthemen zugeordnet, die aber nur für Visual Basic und C# über Syntaxblöcke verfügen, da die Member nur in verwaltetem Code verfügbar sind. In [!INCLUDE[wrt](../../../includes/wrt-md.md)] verfügen Strukturen nur über Felder. Die [!INCLUDE[wrt](../../../includes/wrt-md.md)] Struktur muss eine Hilfsklasse [Windows.UI.Xaml.GridLengthHelper](http://go.microsoft.com/fwlink/p/?LinkId=251060), um die entsprechende Funktionalität bereitzustellen. Sie sehen diese Hilfsklasse in der IDE nicht, wenn Sie verwalteten Code schreiben.  
  
-   In der IDE [!INCLUDE[wrt](../../../includes/wrt-md.md)] Typen ableiten scheinbar <xref:System.Object?displayProperty=fullName>. Sie scheinen von geerbten Member haben <xref:System.Object>, wie z. B. <xref:System.Object.ToString%2A?displayProperty=fullName>. Diese Member können verwendet werden, als die Typen tatsächlich wären von geerbt <xref:System.Object>, und [!INCLUDE[wrt](../../../includes/wrt-md.md)] Typen umgewandelt werden können, um <xref:System.Object>. Diese Funktionalität ist Teil der Unterstützung, die .NET Framework für [!INCLUDE[wrt](../../../includes/wrt-md.md)] bietet. Wenn Sie die Typen jedoch in der [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Referenzdokumentation anzeigen, werden keine solchen Member angezeigt. Die Dokumentation für diese scheinbar geerbten Member erfolgt über die <xref:System.Object?displayProperty=fullName> Referenzdokumentation.  
  
<a name="DifferencesVisibleInIDE"></a>   
### <a name="differences-that-are-visible-in-the-ide"></a>Unterschiede, die in der IDE angezeigt werden  
 In anspruchsvolleren Programmierszenarien, in denen beispielsweise eine in C# geschriebene [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente verwendet wird, um die Anwendungslogik für eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App bereitzustellen, die mithilfe von JavaScript für Windows erstellt wurde, sind solche Unterschiede sowohl in der IDE als auch in der Dokumentation offensichtlich. Wenn die Komponente eine `IDictionary<int, string>`-Schnittstelle an JavaScript zurückgibt und Sie sich diese im JavaScript-Debugger ansehen, sehen Sie die Methoden von `IMap<int, string>`, da JavaScript den [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typ verwendet. In der folgenden Tabelle werden einige häufig verwendete Auflistungstypen aufgeführt, die in den beiden Sprachen unterschiedlich dargestellt werden:  
  
|[!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typ|Entsprechender .NET Framework-Typ|  
|--------------------------------------------------------------|---------------------------------------|  
|`IIterable<T>`|`IEnumerable<T>`|  
|`IIterator<T>`|`IEnumerator<T>`|  
|`IVector<T>`|`IList<T>`|  
|`IVectorView<T>`|`IReadOnlyList<T>`|  
|`IMap<K, V>`|`IDictionary<TKey, TValue>`|  
|`IMapView<K, V>`|`IReadOnlyDictionary<TKey, TValue>`|  
|`IBindableIterable`|`IEnumerable`|  
|`IBindableVector`|`IList`|  
|`Windows.UI.Xaml.Data.INotifyPropertyChanged`|`System.ComponentModel.INotifyPropertyChanged`|  
|`Windows.UI.Xaml.Data.PropertyChangedEventHandler`|`System.ComponentModel.PropertyChangedEventHandler`|  
|`Windows.UI.Xaml.Data.PropertyChangedEventArgs`|`System.ComponentModel.PropertyChangedEventArgs`|  
  
 In [!INCLUDE[wrt](../../../includes/wrt-md.md)] werden `IMap<K, V>` und `IMapView<K, V>` mithilfe von `IKeyValuePair` durchlaufen. Wenn Sie sie an verwalteten Code übergeben, werden sie als `IDictionary<TKey, TValue>` und `IReadOnlyDictionary<TKey, TValue>` angezeigt. Daher können Sie `System.Collections.Generic.KeyValuePair<TKey, TValue>` verwenden, um sie aufzulisten.  
  
 Die Darstellungsweise von Schnittstellen in verwaltetem Code wirkt sich auf die Darstellungsweise der Typen aus, die diese Schnittstellen implementieren. Beispielsweise implementiert die `PropertySet`-Klasse den Typ `IMap<K, V>`, der in verwaltetem Code als `IDictionary<TKey, TValue>` angezeigt wird. `PropertySet` wird angezeigt, als ob es `IDictionary<TKey, TValue>` anstelle von `IMap<K, V>` implementiert. In verwaltetem Code verfügt die Klasse scheinbar über eine `Add`-Methode, die sich wie die `Add`-Methode in .NET Framework-Wörterbüchern verhält. Eine `Insert`-Methode ist scheinbar nicht vorhanden.  
  
 Weitere Informationen zur Verwendung von .NET Framework zum Erstellen einer [!INCLUDE[wrt](../../../includes/wrt-md.md)] Komponente und eine exemplarische Vorgehensweise, die zeigt, wie Sie eine solche Komponente mit JavaScript finden Sie unter [Erstellen von Windows-Runtime-Komponenten in c# und Visual Basic](http://go.microsoft.com/fwlink/p/?LinkId=238313) im Windows Developer Center.  
  
### <a name="primitive-types"></a>Primitive Typen  
 Im Code werden primitive Typen von .NET Framework statt von [!INCLUDE[wrt](../../../includes/wrt-md.md)] angezeigt, damit [!INCLUDE[wrt](../../../includes/wrt-md.md)] in verwaltetem Code einfacher zu verwenden ist. In .NET Framework haben primitive Typen wie die `Int32`-Struktur viele nützliche Eigenschaften und Methoden, beispielsweise die `Int32.TryParse`-Methode. Im Gegensatz dazu verfügen primitive Typen und Strukturen in [!INCLUDE[wrt](../../../includes/wrt-md.md)] nur über Felder. Wenn Sie primitive Typen in verwaltetem Code verwenden, verhalten sie sich wie .NET Framework-Typen, und Sie können deren Eigenschaften und Methoden wie gewohnt verwenden. Die folgende Liste enthält eine Zusammenfassung:  
  
-   Verwenden Sie für die primitiven [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (eine unveränderliche Auflistung von Unicode-Zeichen), `Enum`, `UInt32`, `UInt64` und `Guid` den Typ mit demselben Namen im `System`-Namespace.  
  
-   Verwenden Sie für `UInt8` den Typ `System.Byte`.  
  
-   Verwenden Sie für `Char16` den Typ `System.Char`.  
  
-   Verwenden Sie für die `IInspectable`-Schnittstelle `System.Object`.  
  
-   Verwenden Sie für `HRESULT` eine Struktur mit einem `System.Int32`-Member.  
  
 Wie bei Schnittstellentypen können Sie nur dann einen Beweis für diese Darstellung sehen, wenn es sich bei Ihrem .NET Framework-Projekt um eine [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente handelt, die von einer mit JavaScript erstellten [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App verwendet wird.  
  
 Weitere grundlegende, häufig verwendete [!INCLUDE[wrt](../../../includes/wrt-md.md)] Typen, die in verwaltetem Code, z. B. die .NET Framework-Entsprechungen der `Windows.Foundation.DateTime` -Struktur, die in verwaltetem Code als angezeigt wird die <xref:System.DateTimeOffset?displayProperty=fullName> -Struktur, und die `Windows.Foundation.TimeSpan` -Struktur, die als angezeigt wird die <xref:System.TimeSpan?displayProperty=fullName> Struktur.  
  
### <a name="other-differences"></a>Weitere Unterschiede  
 In einigen wenigen Fällen erfordert die Tatsache, dass im Code .NET Framework-Typen statt [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen dargestellt werden, eine Aktion Ihrerseits. Zum Beispiel die [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) Klasse wird als <xref:System.Uri?displayProperty=fullName> in .NET Framework-Code. <xref:System.Uri?displayProperty=fullName> ein relativer URI, aber [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) muss einen absoluten URI. Wenn Sie einen URI an eine [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Methode übergeben, müssen Sie daher sicherstellen, dass es sich um einen absoluten URI handelt. (Siehe [übergeben eines URI an Windows-Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)  
  
<a name="WindowsRuntimeComponents"></a>   
## <a name="scenarios-for-developing-windows-runtime-components"></a>Szenarien für die Entwicklung von Komponenten für Windows-Runtime  
 Die Szenarien, die für verwaltete [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten unterstützt werden, sind abhängig von den folgenden allgemeinen Prinzipien:  
  
-   Es bestehen keine offensichtlichen Unterschiede zwischen [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten, die mit .NET Framework erstellt wurden, und anderen [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Bibliotheken. Wenn Sie beispielsweise eine systemeigene [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente mit verwaltetem Code erneut implementieren, sind die beiden Komponenten äußerlich nicht zu unterscheiden. Die Tatsache, dass die Komponente in verwaltetem Code geschrieben wurde, ist für den Code, in dem sie verwendet wird, nicht sichtbar, selbst wenn es sich bei diesem Code ebenfalls um verwalteten Code handelt. Intern besteht die Komponente jedoch aus echtem verwaltetem Code und wird von der Common Language Runtime (CLR) ausgeführt.  
  
-   Komponenten können Typen enthalten, die Anwendungslogik, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-UI-Steuerelemente oder beides implementieren.  
  
    > [!NOTE]
    >  Es empfiehlt sich, Benutzeroberflächenelemente von der Anwendungslogik zu trennen. Außerdem können Sie [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-UI-Steuerelemente nicht in einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App verwenden, die mit JavaScript und HTML für Windows erstellt wurde.  
  
-   Eine Komponente kann ein Projekt in einer Visual Studio-Projektmappe für eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App oder eine wiederverwendbare Komponente sein, die Sie mehreren Projektmappen hinzufügen können.  
  
    > [!NOTE]
    >  Wenn die Komponente nur mit C# oder Visual Basic verwendet wird, gibt es keinen Grund, sie als [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente zu erstellen. Wenn Sie sie stattdessen als gewöhnliche .NET Framework-Klassenbibliothek erstellen, müssen Sie die öffentliche API-Schnittstelle nicht auf [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen einschränken.  
  
-   Sie können Versionen wieder verwendbare Komponenten freigeben, indem Sie mit der [!INCLUDE[wrt](../../../includes/wrt-md.md)] [VersionAttribute](http://go.microsoft.com/fwlink/p/?LinkId=238563) Attribut identifiziert die Typen (und Member innerhalb eines Typs) in verschiedenen Versionen hinzugefügt wurden.  
  
-   Die Typen in der Komponente können von [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen abgeleitet werden. Steuerelemente können von primitiven Steuerelementtypen im Ableiten der [Windows.UI.Xaml.Controls.Primitives](http://go.microsoft.com/fwlink/p/?LinkId=238564) Namespace oder aus mehreren Steuerelementen wie z. B. [Schaltfläche](http://go.microsoft.com/fwlink/p/?LinkId=238565).  
  
    > [!IMPORTANT]
    >  Ab [!INCLUDE[win8](../../../includes/win8-md.md)] und [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] müssen alle öffentlichen Typen in einer verwalteten [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente versiegelt werden. Ein Typ in einer anderen [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente kann nicht von ihnen abgeleitet werden. Wenn Sie polymorphes Verhalten in der Komponente ermöglichen möchten, können Sie eine Schnittstelle erstellen und sie in polymorphen Typen implementieren.  
  
-   Alle Parameter und Rückgabetypen für die öffentlichen Typen in der Komponente müssen [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen sein (einschließlich der [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen, die die Komponente definiert).  
  
 Die folgenden Abschnitte enthalten Beispiele für häufig vorkommende Szenarien.  
  
### <a name="application-logic-for-a-includewin8appnamelongtokenwin8appnamelongmdmd-app-with-javascript"></a>Anwendungslogik für eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App mit JavaScript  
 Wenn Sie eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App für Windows mit JavaScript entwickeln, stellen Sie möglicherweise fest, dass einige Teile der Anwendungslogik in verwaltetem Code eine bessere Leistung bieten oder einfacher entwickelt werden können. JavaScript kann .NET Framework-Klassenbibliotheken nicht direkt verwenden. Sie können die Klassenbibliothek jedoch als WinMD-Datei erstellen. In diesem Szenario ist die [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente ein wesentlicher Bestandteil der App. Daher ist es nicht sinnvoll, Versionsattribute bereitzustellen.  
  
### <a name="reusable-includewin8appnamelongtokenwin8appnamelongmdmd-ui-controls"></a>Wiederverwendbare [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-UI-Steuerelemente  
 Sie können einen Satz verwandter UI-Steuerelemente in einer wiederverwendbaren [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente verpacken. Die Komponente kann eigenständig vermarktet oder als Element in den Apps verwendet werden, die Sie erstellen. In diesem Szenario ist es sinnvoll, verwenden Sie die [!INCLUDE[wrt](../../../includes/wrt-md.md)] [VersionAttribute](http://go.microsoft.com/fwlink/p/?LinkId=238563) Attribut, um die Kompatibilität zu verbessern.  
  
### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Wiederverwendbare Anwendungslogik von vorhandenen .NET Framework-Apps  
 Sie können verwalteten Code aus den vorhandenen Desktop-Apps als eigenständige [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente verpacken. So können Sie die Komponente sowohl in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps verwenden, die mithilfe von C++ oder JavaScript erstellt werden, als auch in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps, die mithilfe von C# oder Visual Basic erstellt werden. Sie sollten die Versionsverwaltung verwenden, wenn der Code in mehreren Szenarien wiederverwendet wird.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[.NET für Windows Store-apps – Übersicht](http://go.microsoft.com/fwlink/p/?LinkId=238312)|Beschreibt die .NET Framework-Typen und -Member, die Sie zum Erstellen von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps und [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten verwenden können. (Im Windows Developer Center)|  
|[Roadmap für Windows Store-apps mit c# oder Visual Basic](http://go.microsoft.com/fwlink/p/?LinkId=242212)|Stellt wichtige Ressourcen bereit, die Ihnen beim Einstieg in die Entwicklung von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps mithilfe von C# oder Visual Basic helfen, darunter auch viele Schnellstartthemen, Richtlinien und Best Practices. (Im Windows Developer Center)|  
|[Entwickeln von Windows Store-apps (VB / C#-/ C++ und XAML)](http://go.microsoft.com/fwlink/p/?LinkId=238311)|Stellt wichtige Ressourcen bereit, die Ihnen beim Einstieg in die Entwicklung von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps mithilfe von C# oder Visual Basic helfen, darunter auch viele Schnellstartthemen, Richtlinien und Best Practices. (Im Windows Developer Center)|  
|[Erstellen von Windows-Runtime-Komponenten in c# und Visual Basic](http://go.microsoft.com/fwlink/p/?LinkId=238313)|Beschreibt die Vorgehensweise beim Erstellen einer [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente mit .NET Framework und erläutert, wie diese als Teil einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App verwendet wird, die für Windows mit JavaScript erstellt wird. Außerdem wird beschrieben, wie Sie diese Kombination mit Visual Studio debuggen können. (Im Windows Developer Center)|  
|[Windows-Runtime-Referenz](http://go.microsoft.com/fwlink/?LinkId=238319)|Die Referenzdokumentation für [!INCLUDE[wrt](../../../includes/wrt-md.md)]. (Im Windows Developer Center)|  
|[Übergeben eines URI an Windows-Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Beschreibt ein Problem, das auftreten kann, wenn Sie einen URI aus verwaltetem Code an [!INCLUDE[wrt](../../../includes/wrt-md.md)] übergeben, und wie Sie es vermeiden können.|
---
title: .NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c49e9a5c4b8785704f8c4cbd1c9b7af10dc0c689
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661780"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime

.NET Framework 4.5 unterstützt eine Reihe von Software Development-Szenarien mit der Windows-Runtime. Diese Szenarien werden in drei Kategorien eingeteilt:

- Entwickeln von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -apps mit XAML-Steuerelemente, wie in beschrieben [Roadmap für Windows Store-apps mit c# oder Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [wie Anleitungen (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), und [.NET für Windows Store-apps – Übersicht ](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- Entwickeln von Klassenbibliotheken zur Verwendung in den [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps, die mit .NET Framework erstellt werden

- Entwickeln von Windows-Runtime-Komponenten, verpackt in. WinMD-Dateien, die von jeder Programmiersprache verwendet werden kann, die die Windows-Runtime unterstützt. Beispielsweise finden Sie unter [Erstellen von Windows Runtime-Komponenten in c# und Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

Dieses Thema beschreibt die Unterstützung für alle drei Kategorien bietet .NET Framework und beschreibt die Szenarien für Windows-Runtime-Komponenten. Der erste Abschnitt enthält grundlegende Informationen über die Beziehung zwischen .NET Framework und Windows-Runtime, und erläutert einige eigentümlichkeiten, die möglicherweise im Hilfesystem und in der IDE auftreten. Die [zweiter Abschnitt](#WindowsRuntimeComponents) werden Szenarios für die Entwicklung von Windows-Runtime-Komponenten erläutert.

## <a name="the-basics"></a>Die Grundlagen

.NET Framework unterstützt die drei Entwicklungsszenarien durch die Bereitstellung zuvor aufgeführten [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], und durch die Unterstützung der Windows-Runtime selbst.

- [.NET Framework und Windows-Runtime-Namespaces](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) bietet eine komprimierte Übersicht über die .NET Framework-Klassenbibliotheken und enthalten nur die Typen und Member, die zum Erstellen können [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps und Windows-Runtime-Komponenten.

  - Wenn Sie Visual Studio (Visual Studio 2012 oder höher) verwenden, um das Entwickeln einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app oder einer Windows-Runtime-Komponente, ein Satz von Verweisassemblys wird sichergestellt, dass Sie nur die relevanten Typen und Member.

  - Dieser gestraffte API-Satz wird vereinfacht. Weitere Funktionen durch das Entfernen von Funktionen, die in .NET Framework dupliziert werden oder Windows-Runtime duplizieren. Beispielsweise sie nur die generischen Versionen von Auflistungstypen enthält, und lässt sich das XML-Document Object Model zugunsten von XML-API des Windows-Runtime festgelegt.

  - Funktionen, die einfach einen Wrapper für die Betriebssystem-API werden ebenfalls entfernt, da die Windows-Runtime auf einfache Weise von verwaltetem Code aufgerufen wird.

  Weitere Informationen zu den [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], finden Sie unter den [.NET für Windows Store-apps – Übersicht](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Weitere Informationen zum API-Auswahlverfahren finden Sie unter den [.NET für Windows Store-apps](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) Eintrag im .NET-Blog.

- Die [Windows-Runtime](/uwp/api/) stellt die Benutzeroberflächenelemente für das Erstellen von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -apps und bietet Zugriff auf Betriebssystemfunktionen. Wie .NET Framework, verfügt der Windows-Runtime Metadaten, mit denen die C# und Visual Basic-Compiler verwendet die Windows-Runtime die Möglichkeit, die sie verwenden die .NET Framework-Klassenbibliotheken. .NET Framework erleichtert es, die Windows-Runtime zu verwenden, durch das Ausblenden einiger Unterschiede:

  - Einige Unterschiede bei Programmiermustern zwischen .NET Framework und die Windows-Runtime, z. B. das Muster für das Hinzufügen und Entfernen von Ereignishandlern, werden ausgeblendet. Sie verwenden einfach das .NET Framework-Muster.

  - Einige Unterschiede bei häufig verwendeten Typen (beispielsweise primitive Typen und Auflistungen) werden ausgeblendet. Verwenden Sie einfach den .NET Framework-Typ, wie unter [Unterschiede, sind in der IDE sichtbar](#DifferencesVisibleInIDE)weiter unten in diesem Artikel.

In den meisten Fällen, die .NET Framework-Unterstützung für die Windows-Runtime ist transparent. Im nächste Abschnitt erläutert einige offensichtliche Unterschiede zwischen verwaltetem Code und die Windows-Runtime.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>.NET Framework und die Windows-Runtime-Referenzdokumentation

Die Windows-Runtime und den .NET Framework-Dokumentationen sind getrennt. Wenn Sie F1 drücken, um die Hilfe zu einem Typ oder einem Member aufzurufen, wird die Referenzdokumentation des entsprechenden Satzes angezeigt. Jedoch wenn Sie durchsuchen den [Windows-Runtime-Referenz](/uwp/api/) Beispiele, in denen verwirrende auftreten:

- Themen wie z. B. die <xref:Windows.Foundation.Collections.IIterable%601> Schnittstelle weisen keine Deklarationssyntax für Visual Basic oder c#. Stattdessen wird ein Hinweis angezeigt, über dem Syntaxabschnitt (in diesem Fall ".NET: Diese Schnittstelle wird als System.Collections.Generic.IEnumerable\<T > "). Dies ist, da .NET Framework und die Windows-Runtime ähnliche Funktionalität mit verschiedenen Schnittstellen bereitstellen. Darüber hinaus gibt es Verhaltensunterschiede: `IIterable` verfügt über eine `First`-Methode anstelle einer <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode zum Zurückgeben des Enumerators. Anstatt eine andere Art der Ausführung einer gängige Aufgabe erlernen, unterstützt .NET Framework der Windows-Runtime dazu verwalteten Code scheinbar den Typ zu verwenden, die, dem Sie kennen. Wird nicht angezeigt, die `IIterable` -Schnittstelle in der IDE und ist daher die einzige Möglichkeit, die auftritt und sie in der Windows-Runtime-Referenzdokumentation, die Dokumentation direkt durchsuchen.

- Die <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> Dokumentation veranschaulicht ein sehr ähnliches Problem: Die Parametertypen scheinen für verschiedene Sprachen unterschiedlich sein. Für C# und Visual Basic sind die Parametertypen <xref:System.String?displayProperty=nameWithType> und <xref:System.Uri?displayProperty=nameWithType>. Auch hier besteht der Grund dafür darin, dass .NET Framework über eigene `String`- und `Uri`-Typen verfügt, und bei solchen häufig verwendeten Typen ist es nicht sinnvoll, .NET Framework-Benutzer zu zwingen, eine andere Art der Ausführung zu erlernen. In der IDE Blendet .NET Framework die entsprechenden Windows-Runtime-Typen.

- In einigen Fällen z. B. die <xref:Windows.UI.Xaml.GridLength> Struktur die, .NET Framework stellt einen Typ mit dem gleichen Namen, aber mehr Funktionalität. Beispielsweise ist `GridLength` eine Gruppe von Konstruktor- und Eigenschaftsthemen zugeordnet, die aber nur für Visual Basic und C# über Syntaxblöcke verfügen, da die Member nur in verwaltetem Code verfügbar sind. In der Windows-Runtime verfügen Strukturen nur Felder. Die Windows-Runtime-Struktur benötigt eine Hilfsklasse, <xref:Windows.UI.Xaml.GridLengthHelper>, um entsprechende Funktionalität bereitzustellen. Sie sehen diese Hilfsklasse in der IDE nicht, wenn Sie verwalteten Code schreiben.

- In der IDE angezeigt werden Windows-Runtime-Typen für die Ableitung <xref:System.Object?displayProperty=nameWithType>. Sie scheinen über Member zu verfügen, die von <xref:System.Object> geerbt wurden, beispielsweise <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Diese Member können verwendet werden, als die Typen tatsächlich wären von geerbt <xref:System.Object>, und Windows-Runtime-Typen umgewandelt werden können, um <xref:System.Object>. Diese Funktion ist Teil der Unterstützung von .NET Framework für die Windows-Runtime. Wenn Sie die Typen in der Windows-Runtime-Referenzdokumentation anzeigen, werden jedoch keine solchen Member angezeigt. Die Dokumentation für diese scheinbar geerbten Member finden Sie in der Referenzdokumentation zu <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>Unterschiede, die in der IDE angezeigt werden

In anspruchsvolleren Programmierszenarien, z. B. die Verwendung einer Windows-Runtime-Komponente, die in geschriebenen C# , geben Sie die Anwendungslogik für eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app für Windows mit JavaScript erstellt wurden, sind solche Unterschiede in der IDE als auch deutlich, wie in der Dokumentation. Wenn Ihre Komponente zurückgibt, eine `IDictionary<int, string>` JavaScript, und Sie in der JavaScript-Debugger ansehen, sehen Sie die Methoden der `IMap<int, string>` Da JavaScript den Windows-Runtime-Typ verwendet. In der folgenden Tabelle werden einige häufig verwendete Auflistungstypen aufgeführt, die in den beiden Sprachen unterschiedlich dargestellt werden:

|Windows-Runtime-Typ|Entsprechender .NET Framework-Typ|
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

In der Windows-Runtime `IMap<K, V>` und `IMapView<K, V>` durchlaufen, mit `IKeyValuePair`. Wenn Sie sie an verwalteten Code übergeben, werden sie als `IDictionary<TKey, TValue>` und `IReadOnlyDictionary<TKey, TValue>` angezeigt. Daher können Sie `System.Collections.Generic.KeyValuePair<TKey, TValue>` verwenden, um sie aufzulisten.

Die Darstellungsweise von Schnittstellen in verwaltetem Code wirkt sich auf die Darstellungsweise der Typen aus, die diese Schnittstellen implementieren. Die `PropertySet`-Klasse implementiert beispielsweise `IMap<K, V>`, die in verwaltetem Code als `IDictionary<TKey, TValue>` angezeigt wird. `PropertySet` wird so dargestellt, als ob `IDictionary<TKey, TValue>` statt `IMap<K, V>` von ihr implementiert wurde. Daher wird sie in verwaltetem Code mit einer `Add`-Methode angezeigt, die sich wie die `Add`-Methode für .NET Framework-Wörterbücher verhält. Eine `Insert`-Methode ist scheinbar nicht vorhanden.

Weitere Informationen zur Verwendung von .NET Framework zum Erstellen einer Windows-Runtime-Komponente und eine exemplarische Vorgehensweise, die zeigt, wie Sie eine solche Komponente mit JavaScript verwenden, finden Sie unter [Erstellen von Windows Runtime-Komponenten in C# und Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Primitive Typen

Um die natürliche Verwendung der Windows-Runtime in verwaltetem Code zu aktivieren, werden Sie .NET Framework-primitive Typen anstelle der Windows-Runtime primitiven Typen im Code angezeigt. In .NET Framework haben primitive Typen wie die `Int32`-Struktur viele nützliche Eigenschaften und Methoden, wie die `Int32.TryParse`-Methode. Im Gegensatz dazu haben primitive Typen und Strukturen in der Windows-Runtime nur Felder. Wenn Sie primitive Typen in verwaltetem Code verwenden, verhalten sie sich wie .NET Framework-Typen, und Sie können deren Eigenschaften und Methoden wie gewohnt verwenden. Die folgende Liste enthält eine Zusammenfassung:

- Für die Windows-Runtime-primitive `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (eine unveränderliche Auflistung von Unicode-Zeichen), `Enum`, `UInt32`, `UInt64`, und `Guid`, verwenden Sie den Typ mit dem gleichen Namen in der `System` Namespace.

- Verwenden Sie für `UInt8` den Typ `System.Byte`.

- Verwenden Sie für `Char16` den Typ `System.Char`.

- Verwenden Sie für die `IInspectable`-Schnittstelle `System.Object`.

- Verwenden Sie für `HRESULT` eine Struktur mit einem `System.Int32`-Member.

Wie bei Schnittstellentypen nur dann Sie sehen können, Beweis für diese Darstellung ist, wenn Ihr Projekt .NET Framework eine Komponente für Windows-Runtime, mit dem eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app mit JavaScript erstellt wurden.

Andere grundlegende, häufig verwendeten Windows-Runtime-Typen, die in angezeigt werden von verwaltetem Code als ihre .NET Framework-Entsprechungen zählen die `Windows.Foundation.DateTime` -Struktur, die in verwaltetem Code als wird angezeigt, die <xref:System.DateTimeOffset?displayProperty=nameWithType> Struktur, und die `Windows.Foundation.TimeSpan` Struktur, die wird als die <xref:System.TimeSpan?displayProperty=nameWithType> Struktur.

### <a name="other-differences"></a>Weitere Unterschiede

In einigen Fällen ist die Tatsache, die .NET Framework-Typen im Code anstelle von Windows-Runtime-Typen angezeigt werden Eingriff Ihrerseits erforderlich. Z. B. die <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse angezeigt wird, als <xref:System.Uri?displayProperty=nameWithType> in .NET Framework-Code. <xref:System.Uri?displayProperty=nameWithType> ein relativer URI, aber <xref:Windows.Foundation.Uri?displayProperty=nameWithType> ein absoluter URI erforderlich. Aus diesem Grund, wenn Sie einen URI an eine Windows-Runtime-Methode übergeben, müssen Sie sicherstellen, dass es absolut ist. (Finden Sie unter [übergeben eines URI an der Windows-Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Szenarien für die Entwicklung von Komponenten für Windows-Runtime

Die Szenarien, die für verwaltete Windows-Runtime-Komponenten unterstützt werden, hängen von den folgenden allgemeinen Prinzipien:

- Windows-Runtime-Komponenten, die mithilfe von .NET Framework erstellt wurden, haben keine offensichtlichen Unterschiede zwischen anderen Windows-Runtimelibraries. Wenn Sie eine systemeigene Windows-Runtime-Komponente erneut implementieren mit verwaltetem Code, sind beispielsweise die beiden Komponenten äußerlich nicht zu unterscheiden. Die Tatsache, dass die Komponente in verwaltetem Code geschrieben wurde, ist für den Code, in dem sie verwendet wird, nicht sichtbar, selbst wenn es sich bei diesem Code ebenfalls um verwalteten Code handelt. Intern besteht die Komponente jedoch aus echtem verwaltetem Code und wird von der Common Language Runtime (CLR) ausgeführt.

- Komponenten können Typen enthalten, die Anwendungslogik, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-UI-Steuerelemente oder beides implementieren.

  > [!NOTE]
  > Es empfiehlt sich, Benutzeroberflächenelemente von der Anwendungslogik zu trennen. Außerdem können Sie [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-UI-Steuerelemente nicht in einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App verwenden, die mit JavaScript und HTML für Windows erstellt wurde.

- Eine Komponente kann ein Projekt in einer Visual Studio-Projektmappe für eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App oder eine wiederverwendbare Komponente sein, die Sie mehreren Projektmappen hinzufügen können.

  > [!NOTE]
  > Wenn die Komponente nur mit verwendet wird C# oder Visual Basic gibt es keinen Grund, eine Windows-Runtime-Komponente zu erleichtern. Wenn Sie eine gewöhnliche .NET Framework-Klassenbibliothek stattdessen vereinfachen, müssen Sie die öffentliche API-Oberfläche auf Windows-Runtime-Typen zu beschränken.

- Sie können Versionen von wiederverwendbaren Komponenten freigeben, mithilfe der Windows-Runtime <xref:Windows.Foundation.Metadata.VersionAttribute> Attribut identifiziert die Typen (und Member innerhalb eines Typs) in verschiedenen Versionen hinzugefügt wurden.

- Die Typen in der Komponente können von Windows-Runtime-Typen ableiten. Steuerelemente können von primitiven Steuerelementtypen im Ableiten der <xref:Windows.UI.Xaml.Controls.Primitives> Namespace oder von mehreren Steuerelementen wie z. B. <xref:Windows.UI.Xaml.Controls.Button>.

  > [!IMPORTANT]
  > Beginnend mit [!INCLUDE[win8](../../../includes/win8-md.md)] und .NET Framework 4.5, alle öffentlichen Typen in einer verwalteten Windows-Runtime-Komponente muss versiegelt werden. Ein Typ in einer anderen Windows-Runtime-Komponente kann nicht von ihnen abgeleitet werden. Wenn Sie polymorphes Verhalten in der Komponente ermöglichen möchten, können Sie eine Schnittstelle erstellen und sie in polymorphen Typen implementieren.

- Alle Parameter und Rückgabetypen-Typen für die öffentlichen Typen in der Komponente muss auf den Windows-Runtime-Typen (einschließlich der Windows-Runtime-Typen, die Ihre Komponente definiert).

Die folgenden Abschnitte enthalten Beispiele für häufig vorkommende Szenarien.

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>Anwendungslogik für eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App mit JavaScript

Wenn Sie eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App für Windows mit JavaScript entwickeln, stellen Sie möglicherweise fest, dass einige Teile der Anwendungslogik in verwaltetem Code eine bessere Leistung bieten oder einfacher entwickelt werden können. JavaScript kann .NET Framework-Klassenbibliotheken nicht direkt verwenden. Sie können die Klassenbibliothek jedoch als WinMD-Datei erstellen. In diesem Szenario ist die Windows-Runtime-Komponente ein wesentlicher Bestandteil der app, sodass es sinnvoll, Versionsattribute bereitzustellen nicht.

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>Wiederverwendbare [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-UI-Steuerelemente

Sie können einen Satz von verwandter UI-Steuerelemente in eine wiederverwendbare Komponente der Windows-Runtime verpacken. Die Komponente kann eigenständig vermarktet oder als Element in den Apps verwendet werden, die Sie erstellen. In diesem Szenario wird es sinnvoll, die Verwendung der Windows-Runtime <xref:Windows.Foundation.Metadata.VersionAttribute> Attribut, um die Kompatibilität zu verbessern.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Wiederverwendbare Anwendungslogik von vorhandenen .NET Framework-Apps

Sie können verwalteten Code aus Ihrer vorhandenen desktop-apps als eigenständige Windows-Runtime-Komponente verpacken. So können Sie die Komponente sowohl in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps verwenden, die mithilfe von C++ oder JavaScript erstellt werden, als auch in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps, die mithilfe von C# oder Visual Basic erstellt werden. Sie sollten die Versionsverwaltung verwenden, wenn der Code in mehreren Szenarien wiederverwendet wird.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[.NET für Windows Store-Apps – Übersicht](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Beschreibt die .NET Framework-Typen und Member, die Sie verwenden können, erstellen [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps und Windows-RuntimeComponents. (Im Windows Developer Center)|
|[Roadmap für Windows Store-apps mit c# oder Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Stellt wichtige Ressourcen bereit, die Ihnen beim Einstieg in die Entwicklung von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps mithilfe von C# oder Visual Basic helfen, darunter auch viele Schnellstartthemen, Richtlinien und Best Practices. (Im Windows Developer Center)|
|[Wie Anleitungen (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Stellt wichtige Ressourcen bereit, die Ihnen beim Einstieg in die Entwicklung von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps mithilfe von C# oder Visual Basic helfen, darunter auch viele Schnellstartthemen, Richtlinien und Best Practices. (Im Windows Developer Center)|
|[Erstellen von Windows-Runtime-Komponenten in C# und Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Beschreibt, wie Sie eine Windows-Runtime-Komponente, die mithilfe von .NET Framework zu erstellen, wird erläutert, wie für die Verwendung als Teil einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app für Windows mit JavaScript erstellt, und beschreibt, wie die Kombination mit Visual Studio zu debuggen. (Im Windows Developer Center)|
|[Windows-Runtime-Referenz](/uwp/api/)|Die Referenzdokumentation für die Windows-Runtime. (Im Windows Developer Center)|
|[Übergeben eines URI an Windows-Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Beschreibt ein Problem, die auftreten können, wenn Sie einen URI aus verwaltetem Code an die Windows-Runtime und wie Sie es vermeiden übergeben.|

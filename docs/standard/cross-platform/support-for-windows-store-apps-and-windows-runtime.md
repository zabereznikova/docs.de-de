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
ms.openlocfilehash: 15d6262fb5e7dfb99759f0f85c9a197157713300
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204956"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime

Der .NET Framework 4,5 unterstützt eine Reihe von Software Entwicklungsszenarien mit dem Windows-Runtime. Diese Szenarien werden in drei Kategorien eingeteilt:

- Entwickeln von Windows 8. x Store-Apps mit XAML-Steuerelementen, wie in [Roadmap for Windows C# Store Apps using or Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [How TOS (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))und [.net for Windows Store Apps Overview](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))(in der Roadmap für Windows Store-Apps) beschrieben.

- Entwickeln von Klassenbibliotheken für die Verwendung in den Windows 8. x Store-Apps, die Sie mit dem .NET Framework erstellen.

- Entwickeln von Windows-Runtime-Komponenten, verpackt in. Winmd-Dateien, die von jeder Programmiersprache verwendet werden können, die die Windows-Runtime unterstützt. Informationen hierzu finden Sie beispielsweise [unter Erstellen C# von Windows-Runtime Komponenten in und Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

In diesem Thema wird die Unterstützung erläutert, die der .NET Framework für alle drei Kategorien bietet, und es werden die Szenarien für Windows-Runtime Komponenten beschrieben. Der erste Abschnitt enthält grundlegende Informationen über die Beziehung zwischen dem .NET Framework und dem Windows-Runtime und erläutert einige Eigentümlichkeiten, die im Hilfesystem und in der IDE auftreten können. Im [zweiten Abschnitt](#WindowsRuntimeComponents) werden Szenarien für die Entwicklung von Windows-Runtime-Komponenten erläutert.

## <a name="the-basics"></a>Die Grundlagen

Der .NET Framework unterstützt die drei zuvor aufgeführten Entwicklungsszenarien, indem er [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]bereitstellt und die Windows-Runtime selbst unterstützt.

- [.NET Framework und Windows-Runtime Namespaces](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) bietet eine optimierte Ansicht der .NET Framework-Klassenbibliotheken und umfasst nur die Typen und Member, die Sie zum Erstellen von Windows 8. x Store-Apps und Windows-Runtime Komponenten verwenden können.

  - Wenn Sie Visual Studio (Visual Studio 2012 oder höher) verwenden, um eine Windows 8. x Store-App oder eine Windows-Runtime Komponente zu entwickeln, stellt ein Satz von Verweisassemblys sicher, dass nur die relevanten Typen und Member angezeigt werden.

  - Dieser optimierte API-Satz wird durch das Entfernen von Features, die in der .NET Framework dupliziert werden, und das Duplizieren Windows-Runtime Features weiter vereinfacht. Er enthält z. b. nur die generischen Versionen von Auflistungs Typen, und das XML-Dokument Objektmodell wird zugunsten des Windows-Runtime XML-API-Satzes entfernt.

  - Funktionen, die einfach die Betriebssystem-API einbinden, werden ebenfalls entfernt, da die Windows-Runtime einfach aus verwaltetem Code aufgerufen werden kann.

  Weitere Informationen zum [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]finden Sie in der [Übersicht über .net für Windows Store-Apps](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Weitere Informationen zum API-Auswahlprozess finden Sie im .net [-Blog für apps im Metro-Stil](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) .

- Der [Windows-Runtime](/uwp/api/) stellt die Benutzeroberflächen Elemente zum Entwickeln von Windows 8. x Store-Apps bereit und ermöglicht den Zugriff auf Betriebssystemfunktionen. Wie die .NET Framework verfügt der Windows-Runtime über Metadaten, die es C# den-und-Visual Basic-Compilern ermöglichen, die Windows-Runtime so zu verwenden, wie Sie die .NET Framework-Klassenbibliotheken verwenden. Der .NET Framework erleichtert die Verwendung der Windows-Runtime, indem einige Unterschiede ausgeblendet werden:

  - Einige Unterschiede bei den Programmier Mustern zwischen dem .NET Framework und Windows-Runtime, wie z. b. dem Muster zum Hinzufügen und Entfernen von Ereignis Handlern, werden ausgeblendet. Sie verwenden einfach das .NET Framework-Muster.

  - Einige Unterschiede bei häufig verwendeten Typen (beispielsweise primitive Typen und Auflistungen) werden ausgeblendet. Sie verwenden einfach den .NET Framework-Typ, wie [unter Unterschiede, die in der IDE sichtbar sind](#DifferencesVisibleInIDE), weiter unten in diesem Artikel erläutert werden.

In den meisten Fällen ist .NET Framework Unterstützung für die Windows-Runtime transparent. Im nächsten Abschnitt werden einige der offensichtlichen Unterschiede zwischen verwaltetem Code und dem Windows-Runtime erläutert.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>Die .NET Framework und die Windows-Runtime Referenz Dokumentation

Die Windows-Runtime und die .NET Framework Dokumentations Sätze sind separat. Wenn Sie F1 drücken, um die Hilfe zu einem Typ oder einem Member aufzurufen, wird die Referenzdokumentation des entsprechenden Satzes angezeigt. Wenn Sie jedoch die [Windows-Runtime Referenz](/uwp/api/) durchsuchen, können Sie auf Beispiele stoßen, die verwirrend erscheinen:

- Themen wie die <xref:Windows.Foundation.Collections.IIterable%601>-Schnittstelle weisen keine Deklarations Syntax für C#Visual Basic oder auf. Stattdessen wird ein Hinweis oberhalb des Syntax Abschnitts angezeigt (in diesem Fall ".net: Diese Schnittstelle wird als System. Collections. Generic. IEnumerable\<t >" angezeigt). Dies liegt daran, dass die .NET Framework und die Windows-Runtime ähnliche Funktionen mit unterschiedlichen Schnittstellen bereitstellen. Darüber hinaus gibt es Verhaltensunterschiede: `IIterable` verfügt über eine `First`-Methode anstelle einer <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode zum Zurückgeben des Enumerators. Anstatt eine andere Art der Ausführung einer allgemeinen Aufgabe zu erlernen, unterstützt der .NET Framework die Windows-Runtime, indem der verwaltete Code den Typ verwendet, mit dem Sie vertraut sind. Die `IIterable`-Schnittstelle wird in der IDE nicht angezeigt, weshalb Sie in der Windows-Runtime Referenz Dokumentation nur darauf stoßen können, indem Sie diese Dokumentation direkt durchsuchen.

- Die <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> Dokumentation veranschaulicht ein eng verwandtes Problem: die Parametertypen scheinen für verschiedene Sprachen unterschiedlich zu sein. Für C# und Visual Basic sind die Parametertypen <xref:System.String?displayProperty=nameWithType> und <xref:System.Uri?displayProperty=nameWithType>. Auch hier besteht der Grund dafür darin, dass .NET Framework über eigene `String`- und `Uri`-Typen verfügt, und bei solchen häufig verwendeten Typen ist es nicht sinnvoll, .NET Framework-Benutzer zu zwingen, eine andere Art der Ausführung zu erlernen. In der IDE blendet der .NET Framework die entsprechenden Windows-Runtime Typen aus.

- In einigen Fällen, wie z. b. der <xref:Windows.UI.Xaml.GridLength> Struktur, bietet die .NET Framework einen Typ mit demselben Namen, aber mehr Funktionalität. Beispielsweise ist `GridLength` eine Gruppe von Konstruktor- und Eigenschaftsthemen zugeordnet, die aber nur für Visual Basic und C# über Syntaxblöcke verfügen, da die Member nur in verwaltetem Code verfügbar sind. Im Windows-Runtime haben Strukturen nur Felder. Die Windows-Runtime-Struktur erfordert eine Hilfsklasse, <xref:Windows.UI.Xaml.GridLengthHelper>, um eine entsprechende Funktionalität bereitzustellen. Sie sehen diese Hilfsklasse in der IDE nicht, wenn Sie verwalteten Code schreiben.

- In der IDE scheinen Windows-Runtime Typen von <xref:System.Object?displayProperty=nameWithType>abgeleitet zu werden. Sie scheinen über Member zu verfügen, die von <xref:System.Object> geerbt wurden, beispielsweise <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Diese Member funktionieren so, als würden die Typen, die tatsächlich von <xref:System.Object>geerbt wurden, und Windows-Runtime Typen in <xref:System.Object>umgewandelt werden können. Diese Funktion ist Teil der Unterstützung, die der .NET Framework für die Windows-Runtime bereitstellt. Wenn Sie jedoch die Typen in der Windows-Runtime Referenz Dokumentation anzeigen, werden keine derartigen Member angezeigt. Die Dokumentation für diese scheinbar geerbten Member finden Sie in der Referenzdokumentation zu <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>Unterschiede, die in der IDE angezeigt werden

In komplexeren Programmier Szenarien, wie z. b. der Verwendung einer Windows-Runtime C# -Komponente, die in zum Bereitstellen der Anwendungslogik für eine Windows 8. x Store-App, die für Windows mit JavaScript erstellt wurde, verwendet wird, sind diese Unterschiede in der IDE und in der-Dokumentation erkennbar. Wenn die Komponente eine `IDictionary<int, string>` an JavaScript zurückgibt und Sie Sie im JavaScript-Debugger sehen, sehen Sie die Methoden von `IMap<int, string>`, da JavaScript den Windows-Runtime-Typ verwendet. In der folgenden Tabelle werden einige häufig verwendete Auflistungstypen aufgeführt, die in den beiden Sprachen unterschiedlich dargestellt werden:

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

In der Windows-Runtime werden `IMap<K, V>` und `IMapView<K, V>` mithilfe von `IKeyValuePair`durchlaufen. Wenn Sie sie an verwalteten Code übergeben, werden sie als `IDictionary<TKey, TValue>` und `IReadOnlyDictionary<TKey, TValue>` angezeigt. Daher können Sie `System.Collections.Generic.KeyValuePair<TKey, TValue>` verwenden, um sie aufzulisten.

Die Darstellungsweise von Schnittstellen in verwaltetem Code wirkt sich auf die Darstellungsweise der Typen aus, die diese Schnittstellen implementieren. Die `PropertySet`-Klasse implementiert beispielsweise `IMap<K, V>`, die in verwaltetem Code als `IDictionary<TKey, TValue>` angezeigt wird. `PropertySet` wird so angezeigt, als ob es `IDictionary<TKey, TValue>` anstelle von `IMap<K, V>`implementiert hat, sodass es in verwaltetem Code eine `Add`-Methode hat, die sich wie die `Add`-Methode in .NET Framework Wörterbüchern verhält. Eine `Insert`-Methode ist scheinbar nicht vorhanden.

Weitere Informationen zur Verwendung der .NET Framework zum Erstellen einer Windows-Runtime-Komponente sowie eine exemplarische Vorgehensweise, die zeigt, wie eine solche Komponente mit JavaScript verwendet wird, finden Sie unter [Erstellen von Windows-Runtime Komponenten C# in und Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Primitive Datentypen

Um die natürliche Verwendung der Windows-Runtime in verwaltetem Code zu ermöglichen, werden .NET Framework primitive Typen anstelle Windows-Runtime primitiven Typen im Code angezeigt. In .NET Framework haben primitive Typen wie die `Int32`-Struktur viele nützliche Eigenschaften und Methoden, wie die `Int32.TryParse`-Methode. Im Gegensatz dazu haben primitive Typen und Strukturen in der Windows-Runtime nur Felder. Wenn Sie primitive Typen in verwaltetem Code verwenden, verhalten sie sich wie .NET Framework-Typen, und Sie können deren Eigenschaften und Methoden wie gewohnt verwenden. Die folgende Liste enthält eine Zusammenfassung:

- Verwenden Sie für die Windows-Runtime primitiven `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (eine unveränderliche Auflistung von Unicode-Zeichen), `Enum`, `UInt32`, `UInt64`und `Guid`den Typ desselben Namens im `System`-Namespace.

- Verwenden Sie für `UInt8` den Typ `System.Byte`.

- Verwenden Sie für `Char16` den Typ `System.Char`.

- Verwenden Sie für die `IInspectable`-Schnittstelle `System.Object`.

- Verwenden Sie für `HRESULT` eine Struktur mit einem `System.Int32`-Member.

Wie bei Schnittstellentypen ist das einzige Mal, dass es sich bei Ihrem .NET Framework Projekt um eine Windows-Runtime Komponente handelt, die von einer mit JavaScript erstellten Windows 8. x Store-App verwendet wird.

Weitere grundlegende, häufig verwendete Windows-Runtime Typen, die in verwaltetem Code als Ihre .NET Framework Entsprechungen angezeigt werden, enthalten die `Windows.Foundation.DateTime` Struktur, die in verwaltetem Code als <xref:System.DateTimeOffset?displayProperty=nameWithType> Struktur angezeigt wird, und die `Windows.Foundation.TimeSpan` Struktur, die als <xref:System.TimeSpan?displayProperty=nameWithType> Struktur angezeigt wird.

### <a name="other-differences"></a>Weitere Unterschiede

In einigen Fällen erfordert die Tatsache, dass .NET Framework Typen in Ihrem Code statt Windows-Runtime Typen angezeigt werden, eine Aktion Ihrerseits. Beispielsweise wird die <xref:Windows.Foundation.Uri?displayProperty=nameWithType>-Klasse in .NET Framework Code als <xref:System.Uri?displayProperty=nameWithType> angezeigt. <xref:System.Uri?displayProperty=nameWithType> eine relative URI zulässt, aber <xref:Windows.Foundation.Uri?displayProperty=nameWithType> einen absoluten URI erfordert. Wenn Sie einen URI an eine Windows-Runtime Methode übergeben, müssen Sie daher sicherstellen, dass er absolut ist. Weitere Informationen finden [Sie unter Übergeben eines URI an den Windows-Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Szenarien für die Entwicklung von Komponenten für Windows-Runtime

Die Szenarien, die für verwaltete Windows-Runtime-Komponenten unterstützt werden, sind von den folgenden allgemeinen Prinzipien abhängig:

- Windows-Runtime Komponenten, die mit dem .NET Framework erstellt werden, haben keine offensichtlichen Unterschiede zu anderen Windows runtimelibraries-Komponenten. Wenn Sie z. b. eine systemeigene Windows-Runtime Komponente mithilfe von verwaltetem Code erneut implementieren, sind die beiden Komponenten nach außen unterschieden. Die Tatsache, dass die Komponente in verwaltetem Code geschrieben wurde, ist für den Code, in dem sie verwendet wird, nicht sichtbar, selbst wenn es sich bei diesem Code ebenfalls um verwalteten Code handelt. Intern besteht die Komponente jedoch aus echtem verwaltetem Code und wird von der Common Language Runtime (CLR) ausgeführt.

- Komponenten können Typen enthalten, die Anwendungslogik, Benutzeroberflächen Steuerelemente für Windows 8. x-Speicher oder beides implementieren.

  > [!NOTE]
  > Es empfiehlt sich, Benutzeroberflächenelemente von der Anwendungslogik zu trennen. Außerdem können Sie die UI-Steuerelemente von Windows 8. x nicht in einer Windows 8. x Store-App verwenden, die für Windows mit JavaScript und HTML erstellt wurde.

- Eine Komponente kann ein Projekt in einer Visual Studio-Projekt Mappe für eine Windows 8. x Store-App oder eine wiederverwendbare Komponente sein, die Sie mehreren Lösungen hinzufügen können.

  > [!NOTE]
  > Wenn die Komponente nur mit C# oder Visual Basic verwendet wird, gibt es keinen Grund, Sie zu einer Windows-Runtime Komponente zu machen. Wenn Sie stattdessen eine normale .NET Framework-Klassenbibliothek erstellen, müssen Sie die öffentliche API-Oberfläche nicht auf Windows-Runtime Typen einschränken.

- Sie können Versionen von wiederverwendbaren Komponenten veröffentlichen, indem Sie das Windows-Runtime <xref:Windows.Foundation.Metadata.VersionAttribute>-Attribut verwenden, um zu identifizieren, welche Typen (und welche Member innerhalb eines Typs) in verschiedenen Versionen hinzugefügt wurden.

- Die Typen in der Komponente können von Windows-Runtime Typen abgeleitet werden. Steuerelemente können von den primitiven Steuerelement Typen im <xref:Windows.UI.Xaml.Controls.Primitives>-Namespace oder von besser abgeschlossenen Steuerelementen wie <xref:Windows.UI.Xaml.Controls.Button>abgeleitet werden.

  > [!IMPORTANT]
  > Ab [!INCLUDE[win8](../../../includes/win8-md.md)] und .NET Framework 4,5 müssen alle öffentlichen Typen in einer verwalteten Windows-Runtime-Komponente versiegelt sein. Ein Typ in einer anderen Windows-Runtime Komponente kann nicht von Ihnen abgeleitet werden. Wenn Sie polymorphes Verhalten in der Komponente ermöglichen möchten, können Sie eine Schnittstelle erstellen und sie in polymorphen Typen implementieren.

- Alle Parameter und Rückgabe Typen für die öffentlichen Typen in der Komponente müssen Windows-Runtime Typen sein (einschließlich der Windows-Runtime Typen, die von der Komponente definiert werden).

Die folgenden Abschnitte enthalten Beispiele für häufig vorkommende Szenarien.

### <a name="application-logic-for-a-windows-8x-store-app-with-javascript"></a>Anwendungslogik für eine Windows 8. x Store-App mit JavaScript

Wenn Sie eine Windows 8. x Store-App für Windows mithilfe von JavaScript entwickeln, stellen Sie möglicherweise fest, dass einige Teile der Anwendungslogik in verwaltetem Code besser funktionieren oder einfacher zu entwickeln sind. JavaScript kann .NET Framework-Klassenbibliotheken nicht direkt verwenden. Sie können die Klassenbibliothek jedoch als WinMD-Datei erstellen. In diesem Szenario ist die Windows-Runtime Komponente ein wesentlicher Bestandteil der APP, daher ist es nicht sinnvoll, Versions Attribute bereitzustellen.

### <a name="reusable-windows-8x-store-ui-controls"></a>Wiederverwendbare Steuerelemente für Windows 8. x-Speicher

Sie können eine Reihe verwandter UI-Steuerelemente in einer wiederverwendbaren Windows-Runtime Komponente verpacken. Die Komponente kann eigenständig vermarktet oder als Element in den Apps verwendet werden, die Sie erstellen. In diesem Szenario ist es sinnvoll, das Windows-Runtime <xref:Windows.Foundation.Metadata.VersionAttribute>-Attribut zu verwenden, um die Kompatibilität zu verbessern.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Wiederverwendbare Anwendungslogik von vorhandenen .NET Framework-Apps

Sie können verwalteten Code aus Ihren vorhandenen Desktop-Apps als eigenständige Windows-Runtime Komponente verpacken. Dies ermöglicht Ihnen die Verwendung der Komponente in Windows 8. x Store-Apps, C++ die mit oder JavaScript erstellt wurden, sowie in Windows 8. x Store- C# apps, die mit oder Visual Basic erstellt wurden. Sie sollten die Versionsverwaltung verwenden, wenn der Code in mehreren Szenarien wiederverwendet wird.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[.NET für Windows Store-Apps – Übersicht](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Beschreibt die .NET Framework Typen und Member, die Sie zum Erstellen von Windows 8. x Store-Apps und Windows runtimecomponents verwenden können. (Im Windows Developer Center)|
|[Roadmap für Windows Store-Apps C# , die oder Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Bietet wichtige Ressourcen, die Ihnen den Einstieg in die Entwicklung von Windows 8. x Store C# -Apps mithilfe von oder Visual Basic erleichtern, einschließlich vielen Schnellstart Themen, Richtlinien und bewährten Methoden. (Im Windows Developer Center)|
|[Vorgehensweisen (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Bietet wichtige Ressourcen, die Ihnen den Einstieg in die Entwicklung von Windows 8. x Store C# -Apps mithilfe von oder Visual Basic erleichtern, einschließlich vielen Schnellstart Themen, Richtlinien und bewährten Methoden. (Im Windows Developer Center)|
|[Erstellen von Windows-Runtime-Komponenten in C# und Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|In diesem Thema wird beschrieben, wie Sie mithilfe des .NET Framework eine Windows-Runtime Komponente erstellen. Außerdem wird erläutert, wie Sie Sie als Teil einer Windows 8. x Store-App verwenden, die mit JavaScript für Windows erstellt wurde, und wie Sie die Kombination mit Visual Studio debuggen. (Im Windows Developer Center)|
|[Windows-Runtime Referenz](/uwp/api/)|Die Referenz Dokumentation für die Windows-Runtime. (Im Windows Developer Center)|
|[Übergeben eines URI an Windows-Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Beschreibt ein Problem, das auftreten kann, wenn Sie einen URI aus verwaltetem Code an den Windows-Runtime übergeben und wie Sie ihn vermeiden.|

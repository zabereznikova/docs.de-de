---
title: ".NET Kompatibilit&#228;t Diagnose | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: "twsouthwick"
ms.author: "tasou"
manager: "wpickett"
caps.handback.revision: 7
---
# .NET Kompatibilit&#228;t Diagnose
Die .NET Kompatibilität Diagnose sind Roslyn Energieversorgung Analyzer, mit denen Anwendungskompatibilitätsprobleme zwischen .NET Framework-Versionen zu identifizieren. Diese Liste enthält alle Analysen verfügbar sind, jedoch nur eine Teilmenge für jede spezifische Migration gelten. Analysen werden bestimmt, welche Probleme gelten für die geplanten Migration und nur die Oberfläche. Probleme, die sich von Versionen, die betroffen aufzuteilen, finden Sie unter: [Application Compatibility](../../../docs/framework/migration-guide/application-compatibility.md).  
  
 Jedes Problem enthält die folgenden Informationen:  
  
-   Die Beschreibung der Änderung von einer früheren Version.  
  
-   Die Empfehlung ist eine Beschreibung der Auswirkungen der Änderung auf Kunden und ob umgehen zur Verfügung, um die Kompatibilität zwischen Versionen beizubehalten sind.  
  
-   Eine Bewertung, die Änderung wie wichtig ist. Anwendungskompatibilitätsproblem werden wie folgt kategorisiert:  
  
    |||  
    |-|-|  
    |Hauptversion|Eine wesentliche Änderung, die eine große Anzahl von apps beeinflusst oder erhebliche Änderungen des Codes erforderlich.|  
    |Nebenversion|Eine Änderung, die eine kleine Anzahl von apps beeinflusst oder geringfügige Änderungen des Codes erforderlich.|  
    |Grenzfall|Eine Änderung apps unter ganz bestimmten Szenarien ungewöhnlich beeinflusst.|  
    |Transparent|Eine Änderung hat keine nennenswerten Auswirkungen auf Entwickler oder Benutzer der Anwendungsverzeichnis.|  
  
-   Version gibt an, wann die Änderung zunächst in das Framework angezeigt wird. Einige der Änderungen werden zurückgesetzt, und mit ebenfalls angegeben wird.  
  
-   Der Typ der Änderung:  
  
    |||  
    |-|-|  
    |Neuzuweisung|Die Änderung wirkt sich auf apps, die neu kompiliert werden, um eine neue Version von .NET Framework abzielen.|  
    |Laufzeit|Die Änderung wirkt sich auf einer vorhandenen Anwendung, die eine frühere Version von .NET Framework abzielt, aber auf eine höhere Version ausgeführt wird.|  
  
-   Die betroffenen APIS, falls vorhanden.  
  
-   Die IDs der verfügbaren Diagnosen  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: SoapFormatter Hashtable kann nicht deserialisiert werden und ähnliche sortierten Auflistungsobjekte  
  
|||  
|-|-|  
|Details|Die SoapFormatter garantiert nicht, dass Objekte in einer .NET Framework serialisiert Version erfolgreich unter einer anderen Version deserialisiert wird. Insbesondere hinzugefügt einige geordnete Sammlungen (z. B. Hashtable) Elemente zwischen 4.0 und 4.5 so, dass Objekte dieser Typen wären Serialzied mit .NET 4.5 mit .NET 4.0 deserialisiert werden können. Beachten Sie, dass wenn die serialisierten Daten sowohl serialisiert und deserialisiert werden mit der gleichen Version von .NET Framework, kein Problem auftritt.|  
|Vorschlag|SoapFormatter-Serialisierung sollte mit BinaryFormatter Serialisierung oder NetDataContractSerialization flexibel in Bezug auf .NET Framework-Änderungen werden ersetzt werden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> [SoapFormatter.Serialize (Stream-Objekt, Header\<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|Analyzer|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: WPF DataTemplate-Elementen stehen zur Verfügung UIA  
  
|||  
|-|-|  
|Details|Früher waren DataTemplate-Elementen für die Automatisierung der Benutzeroberfläche nicht sichtbar. 4.5 ab, erkennt das UI-Automatisierung dieser Elemente. Dies ist in vielen Fällen hilfreich, aber kann aufteilen, Tests, die UIA-Strukturen, die nicht mit DataTemplate-Elementen abhängig sind.|  
|Vorschlag|Auomation UI-Tests aktualisiert für diese app möglicherweise, um jetzt mit zuvor unsichtbar DataTemplate-Elementen UIA-Struktur zu berücksichtigen. Beispielsweise müssen Tests, die erwarten, dass einige Elemente werden nebeneinander jetzt zuvor unsichtbare UIA Elemente zwischen erwarten. Oder Tests, die bestimmte Anzahl oder Indizes benötigen UIA-Elemente müssen möglicherweise mit neuen Werten aktualisiert.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|Analyzer|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: WPF-im ausgewählten Textfeld Text wird eine andere Farbe, wenn das Textfeld inaktiv ist.  
  
|||  
|-|-|  
|Details|In .NET 4.5, wenn Sie ein WPF-Steuerelement nicht aktiv ist (muss nicht notwendigerweise den Fokus), der markierte Text in das Feld erscheint eine andere Farbe als wenn das Steuerelement aktiv ist.|  
|Vorschlag|Vorherige (.NET 4.0) Verhalten kann wiederhergestellt werden, durch Festlegen der [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/en-us/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) -Eigenschaft auf false festgelegt.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analyzer|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List<>\>. ForEach kann Ausnahme auslösen, wenn Listenelement ändern  
  
|||  
|-|-|  
|Details|Ab .NET 4.5, eine `List<T>.ForEach` Enumerator löst eine InvalidOperationException-Ausnahme aus, wenn ein Element in der aufrufenden Auflistung geändert wird. Früher dies wäre keine Ausnahme ausgelöst, aber zu Racebedingungen führen.|  
|Vorschlag|Im Idealfall sollte Code so ändern Sie die Listen nicht beim Aufzählen von den Elementen, da, die nie ein Vorgang ist, behoben werden. Um das vorherige Verhalten wiederherzustellen, kann jedoch eine app .NET 4.0 als Ziel.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|Analyzer|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: System.Uri Analyse RFC 3987 entspricht  
  
|||  
|-|-|  
|Details|URI-Analyse ist auf verschiedene Weise in .NET 4.5 geändert. Beachten Sie jedoch, dass diese Änderungen wirken sich nur Code für .NET 4.5 auf. Wenn ein binärer .NET 4.0, wird das alte Verhalten beobachtet werden. An den URI-Analyse in .NET 4.5 enthalten:<br /><br /> URI-Analysen werden Normalisierung und zeichenüberprüfung gemäß den neuesten IRI-Regeln in RFC 3987 ausführen.<br /><br /> Unicode-Normalisierungsform C werden nur auf den Hostteil des URIS ausgeführt werden<br /><br /> Ungültige Mailto: URIs wird nun eine Ausnahme auslösen<br /><br /> Nachgestellte Punkte am Ende eines Pfadsegments sind nun erhalten.<br /><br /> `file://`URIs sind nicht mit Escapezeichen versehen die `?` Zeichen<br /><br /> Unicode-Steuerzeichen `U+0080` über `U+009F` werden nicht unterstützt<br /><br /> Kommas `,` oder `%2c` sind nicht automatisch ohne Escapezeichen|  
|Vorschlag|Wenn die alte .NET 4.0-URI-Analyse-Semantik sind erforderlich (sie sind nicht häufig), können sie durch abzielen auf .NET 4.0 verwendet werden. Dies kann mithilfe einer TargetFrameworkAttribute auf die Assembly oder über Visual Studio Projektsystem-Benutzeroberfläche auf der Seite "Projekteigenschaften" erfolgen.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|Analyzer|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: System.Uri Escapezeichen unterstützt RFC 3986 (http://tools.ietf.org/html/rfc3986)  
  
|||  
|-|-|  
|Details|URI Escapezeichen in .NET 4.5 unterstützt geänderten [RFC 3986](http://tools.ietf.org/html/rfc3986). Bestimmte Änderungen umfassen:<br /><br /> `EscapeDataString` versieht reservierte Zeichen basierend auf RFC 3986 mit Escapezeichen.<br /><br /> `EscapeUriString` versieht reservierte Zeichen nicht mit Escapezeichen.<br /><br /> `UnescapeDataString` löst keine Ausnahme aus, wenn eine ungültige Escapesequenz gefunden wird.<br /><br /> Bei nicht reservierten Zeichen mit Escapezeichen werden letztere entfernt.|  
|Vorschlag|Aktualisieren Sie die Anwendung beruht nicht auf UnescapeDataString für eine ungültige Escapesequenz ausgelöst werden soll. Solche Sequenzen müssen direkt nun erkannt werden.<br /><br /> Auf ähnliche Weise erwarten Sie, dass Zeichenfolgen Escaped und URI ohne Escapezeichen und Daten von .NET 4.0 und .NET 4.5 abweichen und nicht sollen für .NET Versionen direkt verglichen werden. Sondern sollten werden analysiert und in einer einzelnen .NET Version normalisiert werden, bevor alle Vergleiche vorgenommen werden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|Analyzer|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: System.Net.PeerToPeer.Collaboration auf Windows 8 nicht verfügbar  
  
|||  
|-|-|  
|Details|Der System.NET.PeerToPeer.Collaboration-Namespace ist nicht verfügbar für Windows 8 oder höher.|  
|Vorschlag|Apps, die Unterstützung für Windows 8 oder höher müssen aktualisiert werden, um nicht von diesem Namespace oder Membern abhängen.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|Analyzer|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: MEF-Kataloge IEnumerable implementieren und kann daher nicht mehr zum Erstellen eines Serialisierungsprogramms verwendet werden  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5, MEF-Kataloge IEnumerable implementieren und daher nicht mehr verwendet werden können, erstellen Sie ein Serialisierungsprogramm (XmlSerializer-Objekt). Wenn Sie versuchen, einen MEF-Katalog zu serialisieren, wird eine Ausnahme ausgelöst.|  
|Vorschlag|Nicht mehr können MEF Sie ein Serialisierungsprogramm erstellen|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: Fehlendes Zielframeworkmoniker führt 4.0 Verhalten  
  
|||  
|-|-|  
|Details|Ohne ein [TargetFrameworkAttribute](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) auf der Assembly Ebene automatisch ausgeführt wird, mit der Semantik der .NET Framework 4.0 (Quirks) angewendet. Um hohe Qualität sicherzustellen, empfiehlt es sich, dass alle Binärdateien explizit zugeschrieben werden eine TargetFrameworkAttribute, die die Version von .NET Framework, mit der Sie erstellt wurden. Beachten Sie, dass eine Zielframeworkmoniker in einer Projektdatei Caues MSBuild automatisch eine TargetFrameworkAttribute angewendet wird.|  
|Vorschlag|Ein [zielframeworkattribut](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) sollte angegeben werden, entweder über das Attribut hinzufügen, direkt auf die Assembly oder durch Angabe eines Zielframeworks in der [Projektdatei oder über Visual Studio Projekt Eigenschaften GUI](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: nicht länger EnableViewStateMac auf False festgelegt.  
  
|||  
|-|-|  
|Details|ASP.NET ermöglicht mehr Entwicklern an `<pages enableViewStateMac="false"/>` oder `<@Page EnableViewStateMac="false" %>`. Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen. Nur apps, die explizit die EnableViewStateMac-Eigenschaft auf False festgelegt sind betroffen.|  
|Vorschlag|EnableViewStateMac muss angenommen werden, um wahr zu sein, und alle resultierenden MAC Fehler aufgelöst werden müssen (wie in erläutert [dies](https://support.microsoft.com/en-us/kb/2915218) Leitlinien, in denen mehrere Auflösungen abhängig von der Ursache MAC Errors enthält).|  
|Bereich|Hauptversion|  
|Version|4.5.2|  
|Typ|Laufzeit|  
|Analyzer|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection<>\>. TryTakeFromAny wird nicht mehr ausgelöst.  
  
|||  
|-|-|  
|Details|Wenn der input Sammlungen abgeschlossen ist, markiert ist `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` nicht mehr gibt-1 zurück und `BlockingCollection<T>.TakeFromAny` nicht mehr löst eine Ausnahme aus. Diese Änderung ermöglicht das Verwenden von Auflistungen, wenn eine der Auflistungen entweder leer oder abgeschlossen ist, die andere Auflistung aber weiterhin abrufbare Elemente enthält.|  
|Vorschlag|Wenn TryTakeFromAny zurückgeben,-1 oder TakeFromAny auslösen Kontrollfluss Zwecken im Fall der eine blockierende Auflistung abgeschlossen verwendet wurden, diese Art von Code sollte nun so geändert werden `.Any(b => b.IsCompleted)` diese Bedingung erkennen.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|[BlockingCollection<>\>. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analyzer|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException nun legt die Position richtig ausgerichtet  
  
|||  
|-|-|  
|Details|Wenn der LoadOptions.SetLineInfo-Wert an die Load-Methode übergeben wird, und ein Validierungsfehler auftritt, enthalten die Eigenschaften XmlSchemaException.LineNumber und XmlSchemaException.LinePosition jetzt Zeileninformationen.|  
|Vorschlag|Ausnahmebehandlungscode, der XmlSchemaException.LineNumber und XmlSchemaException.LinePosition wird davon ausgegangen werden Satz sollte aktualisiert werden, da diese Eigenschaften werden werden nun ordnungsgemäß festgelegt, wenn SetLineInfo beim Laden von XML verwendet wird.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|Analyzer|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities ist jetzt APTCA  
  
|||  
|-|-|  
|Details|Die Assembly wird mit dem AllowPartiallyTrustedCallersAttribute-Attribut markiert.|  
|Vorschlag|Abgeleitete Klassen können nicht mit dem SecurityCriticalAttribute markiert werden. Zuvor mussten abgeleitete Typen mit dem SecurityCriticalAttribute markiert werden. Diese Änderung sollte jedoch keine tatsächlichen Auswirkungen haben.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: WorkFlow 3.0-Typen sind veraltet  
  
|||  
|-|-|  
|Details|Windows Workflow Foundation (WWF) 3.0-APIs (die aus dem Namespace System.Workflow) sind jetzt veraltet.|  
|Vorschlag|Stattdessen sollte die neue WWF 4.0-APIs (in System.Activities) verwendet werden. Ein Beispiel zur Verwendung der neuen APIs finden Sie [hier](https://msdn.microsoft.com/en-us/library/jj205427.aspx) und weitere Anleitung steht [hier](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx). Alternativ, da die WWF-3.0-APIs weiterhin unterstützt werden, verwendet werden, und die Warnung zur Buildzeit vermieden wird, unterdrücken oder mit einem älteren Compiler.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Analyzer|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: Einige WorkFlow- Drag & Drop-APIs sind veraltet  
  
|||  
|-|-|  
|Details|Dieser WorkFlow Drag & Drop-API ist veraltet und compilerwarnungen verursacht, wenn die app vor 4.5 neu erstellt wird.|  
|Vorschlag|Neue [DragDropHelper](https://msdn.microsoft.com/en-us/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx) -APIs, Vorgänge mit mehreren Objekten unterstützen, sollte stattdessen verwendet werden. Alternativ können die Buildwarnungen unterdrückt werden, oder sie können mit einem älteren Compiler vermieden werden. Die APIs werden weiterhin unterstützt.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|Analyzer|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: neue (mehrdeutige) Dispatcher.Invoke Überladungen unterschiedliches Verhalten verursachen  
  
|||  
|-|-|  
|Details|.NET Framework 4.5 fügt neue Überladungen hinzu Dispatcher.Invoke, die einen Parameter vom Typ System.Action enthalten. Vorhandener Code neu kompiliert, lösen Compiler möglicherweise Dispatcher.Invoke Methoden aufrufen, die Delegatparameter Aufrufe Dispatcher.Invoke Methoden mit einem System.Action-Parameter ist. Wenn ein Aufruf eine Dispatcher.Invoke Überladung mit einem Delegatparameter als Aufruf einer Überladung Dispatcher.Invoke mit einem Parameter System.Action behoben wird, können die folgenden Unterschiede im Verhalten auftreten:<br /><br /> Wenn eine Ausnahme auftritt, werden die Dispatcher.UnhandledExceptionFilter und Dispatcher.UnhandledException-Ereignisse nicht ausgelöst. Stattdessen werden Ausnahmen von der UnobservedTaskException-Ereignis behandelt.<br /><br /> Aufrufe an einige Member, z. B. DispatcherOperation.Result, blockiert, bis der Vorgang abgeschlossen wurde.|  
|Vorschlag|Code aufrufenden Dispatcher.Invoke, vermeiden Sie Mehrdeutigkeit (und mögliche Unterschiede Ausnahme behandeln oder blockierende Verhalten) können ein leeres Objekt [] als zweiten Parameter an die Invoke-Aufruf, um sicherzustellen, dass der Auflösung der Überladung der .NET 4.0-Methode übergeben.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|[Dispatcher.Invoke (delegieren, Object\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (-Delegaten TimeSpan-Objekt\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (Delegat, DispatcherPriority, TimeSpan-Objekt\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (, DispatcherPriority, Delegatobjekt\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|Analyzer|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: EncoderParameter Ctor ist veraltet  
  
|||  
|-|-|  
|Details|Die `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` -Konstruktor ist jetzt veraltet und stell Buildwarnungen verwendet.|  
|Vorschlag|Obwohl die `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` Konstruktor funktionieren weiterhin, der folgende Konstruktor sollte stattdessen verwendet werden, um die veraltete Buildwarnung zu vermeiden, beim erneuten Kompilieren von Code mit .NET 4.5-Tools: [EncoderParameter.EncoderParameter (Encoder, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/en-us/library/hh875096\(v=vs.110\).aspx).|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analyzer|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: Änderung des Verhaltens für Task.WaitAll Methoden mit Timeout-Argumenten  
  
|||  
|-|-|  
|Details|Task.WaitAll Verhalten wurde in .NET 4.5 konsistenter gemacht.<br /><br /> In .NET Framework 4 war das Verhalten dieser Methoden inkonsistent. Bei Ablauf des Timeouts ist, wenn eine oder mehrere Aufgaben wurden abgeschlossen oder, bevor der Methodenaufruf abgebrochen hat die Methode eine AggregateException-Ausnahme ausgelöst. Wenn der abgelaufenen Timeoutintervall keine Aufgaben wurden abgeschlossen oder abgebrochen, bevor der Aufruf der Methode, aber eine oder mehrere Aufgaben in diesen Zustand nach dem Methodenaufruf eingetreten, wurde die Methode false zurückgegeben.<br />In .NET Framework 4.5 geben diese methodenüberladungen jetzt false, wenn alle Aufgaben ausgeführt werden, wenn das Timeoutintervall abgelaufen ist, und sie eine Ausnahme AggregateException nur, wenn eine eingabeaufgabe abgebrochen (unabhängig davon, ob es sich vor oder nach dem Aufruf der Methode handelt) und keine anderen Aufgaben noch aktiv sind zurück.|  
|Vorschlag|Wenn AggregateException abgefangen wird wurde, als ein Mittel zum Erkennen von einer Aufgabe, die vor dem WaitAll-Aufruf aufgerufen wird, abgebrochen wurde, dass der Code stattdessen die gleiche Erkennung über die IsCanceled-Eigenschaft geschehen soll (z. B.:. Alle (t => t.IsCanceled)), da .NET 4.6 in diesem Fall nur ausgelöst wird, wenn alle erwartete Aufgaben vor dem Timeout abgeschlossen werden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|[Task.WaitAll (Aufgabe\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [Task.WaitAll (Aufgabe\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [Task.WaitAll (Aufgabe\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analyzer|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: Änderung des Verhaltens in Internetinformationsdienste APIs (Data Definition Language, Datendefinitionssprache)  
  
|||  
|-|-|  
|Details|Das Verhalten von DDL-APIs, falls AttachDBFilename angegeben ist, wurde wie folgt geändert:<br /><br /> Verbindungszeichenfolgen müssen keinen Initial Catalog-Wert angeben. Zuvor waren AttatchDBFilename und Anfangskatalog erforderlich.<br /><br /> Wenn AttatchDBFilename und Anfangskatalog angegeben sind, und die angegebene MDF-Datei vorhanden ist, gibt die Methode ObjectContext.DatabaseExists true zurück. Früher gab es false zurück.<br /><br /> Wenn AttatchDBFilename und Anfangskatalog angegeben sind, und die angegebene MDF-Datei vorhanden ist, die ObjectContext.DeleteDatabase-Methode aufrufen, werden die Dateien gelöscht.<br /><br /> Wenn ObjectContext.DeleteDatabase aufgerufen wird, wenn die Verbindungszeichenfolge gibt einen AttachDBFilename-Wert mit einer MDF-Datei, die nicht vorhanden "und" Initial Catalog-Eigenschaft, die nicht vorhanden ist, löst die Methode eine InvalidOperationException-Ausnahme. Zuvor hat er eine SqlException-Ausnahme ausgelöst.|  
|Vorschlag|Diese Änderungen erleichtern das Erstellen von Tools und Anwendungen, die die DDL-APIs verwenden. Diese Änderungen können sich in den folgenden Szenarien auf die Anwendungskompatibilität auswirken:<br /><br /> Der Benutzer schreibt Code, der einen Befehl DROP DATABASE anstatt aufrufen ObjectContext.DeleteDatabase direkt ausgeführt wird, wenn ObjectContext.DatabaseExists true zurückgibt. Ist die Datenbank nicht angefügt, die MDF-Datei jedoch vorhanden, wird vorhandener Code hierdurch unbrauchbar.<br /><br /> Der Benutzer schreibt Code, der die Methode ObjectContext.DeleteDatabase Ausnahmefehler InvalidOperationException, anstatt eine SqlException-Ausnahme auslöst, wenn es sich bei den Anfangskatalog und die MDF-Datei nicht vorhanden sind.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: MachineKey.Encode und MachineKey.Decode-Methoden sind jetzt veraltet  
  
|||  
|-|-|  
|Details|Diese Methoden sind jetzt veraltet. Die Kompilierung von Code, der diese Methoden aufruft, erzeugt eine Compilerwarnung.|  
|Vorschlag|Die empfohlenen alternativen sind [MachineKey.Protect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) und [MachineKey.Unprotect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx). Alternativ können die Buildwarnungen unterdrückt werden, oder sie können mit einem älteren Compiler vermieden werden. Die APIs werden weiterhin unterstützt.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> [MachineKey.Encode (Byte\<xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|Analyzer|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: die Replace-Methode in OData-URLs ist standardmäßig deaktiviert.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5 ist die Replace-Methode in OData-URLs standardmäßig deaktiviert. Wenn OData ersetzen (jetzt standardmäßig) deaktiviert ist, schlagen alle Benutzeranfragen einschließlich Ersetzungsfunktionen (die nicht üblich sind) fehl.|  
|Vorschlag|Wenn die Replace-Methode erforderlich ist (Dies ist ungewöhnlich), kann es wieder aktiviert ist, über eine [Config-Einstellungen](https://msdn.microsoft.com/en-us/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx). Allerdings wird eine aktivierte Replace-Methode kann Sicherheitslücken öffnen und sollte nur nach sorgfältiger Prüfung verwendet werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|Analyzer|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: System.ServiceModel.Web.WebServiceHost Objekt nicht mehr fügt keinen standardmäßigen Endpunkt  
  
|||  
|-|-|  
|Details|System.ServiceModel.Web.WebServiceHost Objekts fügt einen Standardendpunkt nicht mehr, wenn ein expliziter Endpunkt vom Anwendungscode hinzugefügt wurde.|  
|Vorschlag|Wenn Benutzer erwarten, dass ein Standardendpunkt herstellen kann und andere explizite Endpunkte WebServiceHost hinzugefügt wurden, Standardendpunkte sollte auch hinzugefügt werden, explizit (mit AddDefaultEndpoints).|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|Analyzer|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: EventSource.WriteEvent Impls müssen WriteEvent dieselben Parameter, die Sie (+ ID erhalten) übergeben  
  
|||  
|-|-|  
|Details|Die Laufzeit erzwingt jetzt den Vertrag, der Folgendes angibt: eine Klasse abgeleitet, die eine ETW-Ereignismethode definiert EventSource muss EventSource.WriteEvent-Methode die Basisklasse aufrufen, mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die die ETW-Ereignismethode übergeben wurde.|  
|Vorschlag|Eine Ausnahme IndexOutOfRangeException wird ausgelöst, wenn ein Ereignislisteners EventSource-Daten im Prozess für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Analyzer|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: MinFreeMemoryPercentageToActiveService wird jetzt berücksichtigt.  
  
|||  
|-|-|  
|Details|Diese Einstellung gibt die minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein müssen, bevor ein WCF-Dienst aktiviert werden kann. Es soll OutOfMemoryException-Ausnahmen zu verhindern. In .NET Framework 4.5 hatte diese Einstellung keine Auswirkung. In .NET Framework 4.5.1 wird die Einstellung beobachtet.|  
|Vorschlag|Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist. Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Analyzer|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: XmlTextReader DTD-entitätserweiterung ist auf 10.000.000 Zeichen beschränkt  
  
|||  
|-|-|  
|Details|DTD-entitätserweiterung ist auf 10.000.000 Zeichen beschränkt. Das Laden von XML-Dateien ohne DTD-Entitätserweiterung oder mit eingeschränkter DTD-Entitätserweiterung ist davon nicht betroffen. Dateien mit DTD-Entitäten, die auf mehr als 10.000.000 Zeichen erweitert werden, können nicht geladen werden und lösen nun eine Ausnahme aus.|  
|Vorschlag|Wenn das Limit von DTD-entitätserweiterung 10.000.000 zu niedrig ist, kann der Wert überschrieben werden, mit der [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/en-us/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx) Eigenschaft. Ein "XmlReaderSettings" mit den richtigen MaxCharactersFromEntity Wert übergeben werden kann [XmlReader.Create](https://msdn.microsoft.com/en-us/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx)|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|Analyzer|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: XSLT-Stylesheet Ausnahme Nachricht geändert  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 ist der Text der Fehlermeldung, wenn eine XSLT-Datei zu komplex ist "das Stylesheet ist zu komplex." In früheren Versionen hieß die Fehlermeldung "XSLT-Compilerfehler." Anwendungscode, der vom Text der Fehlermeldung abhängt, funktioniert nicht mehr. Die Ausnahmetypen sind identisch, allerdings so sollte diese Änderung keine tatsächlichen Auswirkungen haben.|  
|Vorschlag|Aktualisieren der app-Code abhängig von der Excepton-Nachricht über diesen Fehlerzustand zu erwarten, dass die neue Nachricht oder (noch besser) aktualisieren Sie den Code so, dass nur der Ausnahmetyp abhängig ([XsltException](https://msdn.microsoft.com/en-us/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx)), die nicht geändert wurde.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|[XslCompiledTransform.Load (MethodInfo, Byte\[\], Typ\<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|Analyzer|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF serialisiert Expressions.Literal<> \</> \> Uhrzeitangaben nun anders (benutzerdefinierte XAML-Parser unterbrochen)  
  
|||  
|-|-|  
|Details|Die zugeordnete [ValueSerializer](https://msdn.microsoft.com/en-us/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) -Objekt konvertiert ein DateTime- oder DateTimeOffset-Objekt, dessen Komponenten für Sekunden und Millisekunden ungleich NULL sind und (für einen datetime-Wert value), deren DateTime.Kind-Eigenschaft nicht Eigenschaftenelementsyntax anstatt in eine Zeichenfolge nicht angegeben ist. Diese Änderung können "DateTime" und "DateTimeOffset"-Werten Round ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|  
|Vorschlag|Diese Änderung können "DateTime" und "DateTimeOffset"-Werten Round ausgeführt werden. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: neue Enumerationswerte in der WPF PageRangeSelection  
  
|||  
|-|-|  
|Details|Zwei neue Elemente (CurrentPage und SelectedPage) wurden hinzugefügt, um die [PageRangeSelection](https://msdn.microsoft.com/en-us/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx) Enum.|  
|Vorschlag|In den meisten Fällen wird nicht diese Änderungen Benutzercode auswirken. Code, der von einer bestimmten Anzahl von Elementen, die im Enum.GetNames oder "Enum.GetValues" abhängt Ruft für die PageRangeSelection Typ sollte, jedoch geändert werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|Analyzer|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: WPF DispatcherSynchronizationContext.CreateCopy gibt nun eine neue Kopie anstelle der aktuellen Instanz zurück  
  
|||  
|-|-|  
|Details|In .NET Framework 4 zurückgegeben DispatcherSynchronizationContext.CreateCopy() einen Verweis auf die aktuelle Instanz, in erster Linie als zur Optimierung der Leistung. In .NET Framework 4.5 wird eine neue Instanz die Möglichkeit zum ersten Mal geschlossen werden, dass gleiche Verweise angeben, dass der Ausführende Thread im richtigen Synchronisierungskontext wird zurückgegeben.  Es ist unwahrscheinlich, dass Code, der die Identität dieser Verweise prüft betroffen, aber aufgrund der Änderung DispatcherSynchronizationContext.CreateCopy aufrufende Code als Teil der Migration zu .NET Framework 4.5 getestet werden oder höher.|  
|Vorschlag|Werden Sie DispatcherSynchronizationContext.CreateCopy() jetzt ein neues SynchronizationContext-Objekt zurück.  Code, mit denen die Äquivalenz von Verweisen auf diese Weise generiert wurde zuvor tatsächlich keine Überprüfung auf, ob er im richtigen Kontext wurde, jedoch wird bei der Erstellung von .NET 4.5 oder höher.  Während es unwahrscheinlich, dass Probleme verursachen, sollte betreffen die betroffenen Codepfade ausreichend, um zu bestimmen, ob dies ein Problem darstellt.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|Analyzer|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: System.Threading.Tasks.Task mehr ObjectDisposedException auslösen, nachdem das Objekt verworfen wird,  
  
|||  
|-|-|  
|Details|Mit Ausnahme von Task.IAsyncResult.AsyncWaitHandle Ausnahme System.Threading.Tasks.Task Methoden nicht mehr eine ObjectDisposedException, nachdem das Objekt verworfen wird.<br />Diese Änderung unterstützt die Verwendung von zwischengespeicherten Aufgaben. Beispielsweise kann eine Methode eine zwischengespeicherte Aufgabe zurückgeben, um einen bereits abgeschlossenen Vorgang darzustellen, anstatt eine neue Aufgabe zuzuordnen. Dies war in früheren .NET Framework-Versionen nicht möglich, da jeder Consumer der Aufgabe diese freigeben konnte und somit unbrauchbar machte.|  
|Vorschlag|Denken Sie daran, dass Task-Methoden nicht mehr auslösen können ObjectDisposedExceptions in Fällen, wenn das Objekt verworfen wird. Wenn eine app je nach wurde diese Ausnahme zu wissen, dass eine Aufgabe gelöscht wurde, sollten sie explizit den Status der Aufgabe überprüfen aktualisiert werden mithilfe von [Task.Status](https://msdn.microsoft.com/en-us/library/system.threading.tasks.task.status\(v=vs.110\).aspx).|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: unterschiedliche Ausnahmebehandlung für ObjectContext.CreateDatabase und DbProviderServices.CreateDatabase-Methode  
  
|||  
|-|-|  
|Details|Ab .NET 4.5, schlägt das Erstellen einer Datenbank `CreateDatabase` Methoden versucht, die leere Datenbank zu löschen. Wenn dieser Vorgang erfolgreich ist, die ursprüngliche `SQLException` weitergegeben (statt der `InvalidOperationException` , die in .NET 4.0 immer ausgelöst wurde)|  
|Vorschlag|Wenn eine InvalidOperationException abfangen während der Ausführung von ObjectContext.CreateDatabase oder DbProviderServices.CreateDatabase, sollten sich nun auch abgefangen werden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analyzer|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: ObjectContext.Translate und ObjectContext.ExecuteStoreQuery unterstützen jetzt die Enum-Typ  
  
|||  
|-|-|  
|Details|In .NET 4.0, des generischen Parameters `T` von `ObjectContext.Translate` und `ObjectContext.ExecuteStoreQuery` Methoden nicht Enum werden konnte. Dieses Szenario wird nun unterstützt.|  
|Vorschlag|Wenn übersetzen oder ExecuteStoreQuery für eine Enum-Typ in .NET 4.0 aufgerufen wurde, wurde '0' zurückgegeben. Wenn dieses Verhalten erwünscht ist, sollte die Aufrufe mit einer Konstante 0 (oder die Enum-Entsprechung des) ersetzt werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|[ObjectContext.ExecuteStoreQuery<>\>(String, Object\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [ObjectContext.ExecuteStoreQuery<>\>(String, String, MergeOption, Objekt\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|Analyzer|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty<> \</> \> immer gibt zwischengespeicherte Instanz  
  
|||  
|-|-|  
|Details|Ab .NET 4.5, `Enumerable.Empty` gibt immer eine zwischengespeicherte interne Instanz `IEnumerable<T>`.<br /><br /> Zuvor `Enumerable.Empty` würde eine leere zwischenspeichern `IEnumerable<T>` zu dem Zeitpunkt, an die API wurde aufgerufen, was bedeutet, dass unter bestimmten Umständen in der `Enumerable.Empty` aufgerufen wurde schnell und gleichzeitig andere Instanzen des Typs können für verschiedene Aufrufe der API zurückgegeben werden.|  
|Vorschlag|Da das vorherige Verhalten nicht deterministisch ist, ist der Code wahrscheinlich davon abhängen. Jedoch in dem unwahrscheinlichen Fall, die leere aufzählbare Elemente bereit, die verglichen werden, und manchmal werden erwartet, explizite leere Arrays erstellt werden soll (`new T[0]`) anstelle von `Enumerable.Empty`.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|Analyzer|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: HttpRequest.ContentEncoding Eigenschaft verhindert UTF7  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5 ist UTF-7-Codierung in Gremien HttpRequests nicht zulässig. Teilweise treten bei Daten für Anwendungen, die von eingehenden UTF-7-Daten abhängen, Decodierungsprobleme auf.|  
|Vorschlag|Im Idealfall sollten Applikationen verwenden Sie UTF-7-Codierung in HttpRequests nicht aktualisiert werden. Alternativ kann Legacyverhalten wiederhergestellt werden, mithilfe der `aspnet:AllowUtf7RequestContentEncoding` -Attribut des der [AppSettings](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) Element.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|Analyzer|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode versieht kaufmännisches und-Zeichen  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5, umgeht JavaScriptStringEncode das kaufmännische und-Zeichen (&) Zeichen.|  
|Vorschlag|Wenn Ihre app auf dem vorherigen Verhalten dieser Methode abhängig ist, können Sie eine Aspnet:JavaScriptDoNotEncodeAmpersand Einstellung hinzufügen der [AppSettings-Element von ASP.NET](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) in der Konfigurationsdatei.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werte ab.  
  
|||  
|-|-|  
|Details|EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werte. NULL-Zeichen werden nicht von der EventSource-Klasse unterstützt. Die Änderung betrifft nur apps, die mit dem EventListener um EventSource-Daten im Prozess zu lesen und, die Null-Zeichen als Trennzeichen verwenden.|  
|Vorschlag|EventSource-Daten sollten nach Möglichkeit aktualisiert werden, um eingebettete Null-Zeichen können nicht verwendet.|  
|Bereich|Kante|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName> \</String, String>|  
|Analyzer|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: ObsoleteAttribute exportiert als ObsoleteAttribute und DeprecatedAttribute in WinMD-Szenarien  
  
|||  
|-|-|  
|Details|Wenn Sie eine Windows-metadatenbibliothek (winmd-Datei) erstellen, wird das ObsoleteAttribute-Attribut als ObsoleteAttribute und Windows.Foundation.DeprecatedAttribute exportiert.|  
|Vorschlag|Neukompilierung des vorhandenen Quellcodes, die das ObsoleteAttribute-Attribut verwendet, generiert möglicherweise Warnungen beim Verarbeiten des Codes in C++ / CX oder JavaScript.<br /><br /> Es wird nicht empfohlen, Code in verwalteten Assemblys ObsoleteAttribute und Windows.Foundation.DeprecatedAttribute zuweisen; Es kann dazu führen, dass Buildwarnungen.|  
|Bereich|Kante|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Analyzer|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: ResolveAssemblyReference-Aufgabe jetzt warnt, Abhängigkeiten mit der falschen Architektur  
  
|||  
|-|-|  
|Details|Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht. Dies geschieht beispielsweise, wenn eine Anwendung, die mit der Option Anycpu kompiliert wurde ein X86 enthält Verweis. Ein solches Szenario kann einen App-Fehler zur Laufzeit ergeben (in diesem Fall, wenn die App als x64-Prozess bereitgestellt wird).|  
|Vorschlag|Es gibt zwei Bereiche mit Auswirkungen:<br /><br /> Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde. Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.<br /><br /> Wenn Warnungen wie Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Analyzer|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: WPF Textfeld standardmäßig maximal 100 rückgängig machen  
  
|||  
|-|-|  
|Details|In .NET 4.5 ist der Rückgängig-Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zum unbegrenzt im .NET 4.0)|  
|Vorschlag|Wenn eine Rückgängig-Grenze von 100 zu niedrig ist, kann der Grenzwert explizit mit UndoLimit-Eigenschaft des Textfelds festgelegt werden|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analyzer|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: Ausnahmen während der nicht überwachte Verarbeitung in System.Threading.Tasks.Task mehr Finalizerthread weitergegeben  
  
|||  
|-|-|  
|Details|Da die System.Threading.Tasks.Task-Klasse einen asynchronen Vorgang darstellt, werden alle nicht schwerwiegenden Ausnahmen, die während der asynchronen Verarbeitung auftreten abgefangen. In .NET Framework 4.5 Wenn eine Ausnahme nicht beachtet, und Ihr Code nie auf die Aufgabe wartet die Ausnahme wird nicht mehr im Finalizerthread weitergegeben und führt den Prozess während der Garbagecollection. Diese Änderung erhöht die Zuverlässigkeit, die Aufgabenklasse verwenden nicht überwachte asynchrone Verarbeitungen ausführen.|  
|Vorschlag|Wenn eine Anwendung nicht überwachte asynchrone Ausnahmen, die Weitergabe an den Finalizerthread abhängig ist, kann das vorherige Verhalten wiederhergestellt werden, indem einem entsprechenden Handler für die [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/en-us/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) Ereignis oder durch Festlegen einer [Common Language Runtime-Konfigurationselement](https://msdn.microsoft.com/en-us/library/jj160346%28v=vs.110%29.aspx).|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|Analyzer|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: IAsyncResult.CompletedSynchronously-Eigenschaft muss korrekt sein, damit die resultierende Aufgabe abgeschlossen  
  
|||  
|-|-|  
|Details|Wenn Sie TaskFactory.FromAsync aufrufen zu können, muss die Implementierung der IAsyncResult.CompletedSynchronously-Eigenschaft für die resultierende Aufgabe abgeschlossen sein. Also muss die Eigenschaft "true" zurückgeben, wenn und nur dann, wenn die Implementierung synchron abgeschlossen wurde. Zuvor wurde die Eigenschaft nicht überprüft.|  
|Vorschlag|Wenn IAsyncResult-Implementierungen ordnungsgemäß für die CompletedSynchronusly-Eigenschaft nur, wenn ein Task synchron abgeschlossen true zurückgeben, wird kein Umbruch beachtet werden. Benutzer sollten IAsyncResult-Implementierung, die sie (sofern vorhanden) besitzen, um sicherzustellen, dass sie, ob eine Aufgabe synchron oder nicht richtig ausgewertet.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> </TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult>|  
|Analyzer|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: Protokolldateinamen erstellt, indem die ObjectContext.CreateDatabase-Methode wurde geändert, um die SQL Server-Spezifikationen entsprechen.  
  
|||  
|-|-|  
|Details|Wenn die CreateDatabase-Methode wird aufgerufen, entweder direkt oder Code First mit dem SqlClient-Anbieter und einen AttachDBFilename-Wert in der Verbindungszeichenfolge verwenden, erstellt es eine Protokolldatei mit dem Namen filename_log.ldf anstelle von Dateiname.ldf (wobei Dateiname den Namen der Datei durch den AttachDBFilename-Wert angegeben ist). Diese Änderung verbessert das Debuggen, indem eine Protokolldatei bereitgestellt wird, die nach den SQL Server-Spezifikationen benannt wird.|  
|Vorschlag|Wenn Sie den Namen der Protokolldatei für eine Anwendung wichtig ist, sollte die app aktualisiert werden, um das standardmäßige _log.ldf Dateinamenformat erwarten.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analyzer|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: Page.LoadComplete-Ereignis wird nicht mehr System.Web.UI.WebControls.EntityDataSource Steuerelement zum Binden von Daten aufrufen.  
  
|||  
|-|-|  
|Details|Die `Page.LoadComplete` Ereignis wird nicht mehr vom System.Web.UI.WebControls.EntityDataSource-Steuerelement datenbindungen für Änderungen erstellen/aktualisieren/löschen-Parametern aufrufen. Diese Änderung schließt unnötige Roundtrips zur Datenbank, verhindert, dass die Werte von Steuerelementen zurückgesetzt und erzeugt Verhaltensweisen, die mit anderen Datensteuerelementen, wie SqlDataSource und ObjectDataSource konsistent ist. Diese Änderung erzeugt im unwahrscheinlichen Fall, dass Anwendungen im `Page.LoadComplete`-Ereignis auf Aufrufen der Datenbindung basieren, ein anderes Verhalten.|  
|Vorschlag|Rufen Sie Notwendigkeit von Databinding vorhanden ist, manuell Databind in ein Ereignis, das das Postback liegt.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode decodiert mehr ungültige Eingabesequenzen  
  
|||  
|-|-|  
|Details|Decodierungsmethoden decodieren nicht mehr standardmäßig ungültige Eingabesequenzen in ungültige UTF-16-Zeichenfolgen. Stattdessen geben sie die ursprüngliche Eingabe zurück.|  
|Vorschlag|Die Änderung der Decoderausgabe sollte nur von Bedeutung sein, wenn Sie Binärdaten statt der UTF-16-Daten in Zeichenfolgen speichern. Um dieses Verhalten explizit zu steuern, legen die `aspnet:AllowRelaxedUnicodeDecoding` -Attribut des der [AppSettings](https://msdn.microsoft.com/en-us/library/ms228154\(v=vs.110\).aspx) Element auf True, um Legacyverhalten aktivieren oder auf "false", um das aktuelle Verhalten zu aktivieren.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|Analyzer|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: mit ClickOnce veröffentlichte apps, die ein SHA-256-Codesignaturzertifikat verwenden möglicherweise unter Windows 2003  
  
|||  
|-|-|  
|Details|Die ausführbare Datei ist mit SHA256 signiert. Früher wurde sie mit SHA1 signiert, unabhängig davon, ob das Codesignaturzertifikat SHA-1 oder SHA-256 war. Dies gilt für:<br /><br /> Alle Anwendungen, die mit Visual Studio 2012 oder höher erstellt wurden.<br /><br /> Anwendungen, die mit Visual Studio 2010 oder früher auf Systemen mit vorhandenem .NET Framework 4.5 erstellt wurden.<br /><br /> Darüber hinaus wird das ClickOnce-Manifest, wenn .NET Framework 4.5 oder höher vorhanden ist, auch mit SHA-256 für SHA-256-Zertifikate signiert, unabhängig von der .NET Framework-Version, mit der es kompiliert wurde.|  
|Vorschlag|Die Änderung bei der Signierung der ausführbaren ClickOnce betrifft nur Windows Server 2003-Systeme. KB 938397 installiert werden müssen.<br /><br /> Die Änderung bei der Signierung des Manifests mit SHA-256, selbst wenn eine App auf .NET Framework 4.0 oder frühere Versionen abzielt, führt eine Laufzeitabhängigkeit von .NET Framework 4.5 oder einer höheren Version ein.|  
|Bereich|Kante|  
|Version|4.5-4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision und DbParameter.Scale sind jetzt öffentliche virtuelle Member  
  
|||  
|-|-|  
|Details|DbParameter.Precision und DbParameter.Scale werden als öffentliche virtuelle Eigenschaften implementiert. Ersetzen sie die entsprechenden expliziten schnittstellenimplementierungen, DbParameter.IDbDataParameter.Precision und DbParameter.IDbDataParameter.Scale.|  
|Vorschlag|Wenn einen ADO.NET-Anbieter für die Datenbank neu zu erstellen, erfordert diese Unterschiede werden das Schlüsselwort 'Überschreiben' auf die Genauigkeit und Dezimalstellenanzahl Eigenschaften angewendet werden. Dies ist nur erforderlich, wenn die Komponenten neu zu erstellen; vorhandene Binärdateien werden weiterhin funktionieren.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|Analyzer|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData ruft nun Daten als UTF-8  
  
|||  
|-|-|  
|Details|Für apps, .NET Framework 4 oder die auf .NET Framework 4.5.1 oder älteren Versionen ausgeführt ruft DataObject.GetData HTML-formatierte Daten als ASCII-Zeichenfolge ab. Als Resultat werden nicht-ASCII-Zeichen (Zeichen mit ASCII-Codes größer als 0x7F) durch zwei zufällige Zeichen dargestellt.<br /><br /> Für apps, die das .NET 4.5 oder höher und auf .NET Framework 4.5.2 Framework, `DataObject.GetData` HTML-formatierte Daten als UTF-8, der Zeichen größer als 0x7F korrekt abruft.|  
|Vorschlag|Wenn Sie eine Lösung für das Codierungsproblem mit HTML-formatierten Zeichenfolgen (z. B. durch explizites Codieren der HTML-Zeichenfolge, die aus der Zwischenablage durch Übergabe an die Methode UTF8Encoding.GetString abgerufen) implementiert und das Ziel Ihrer app von Version 4, 4.5, sollte diese Lösung entfernt werden.<br /><br /> Wenn aus irgendeinem Grund das alte Verhalten erforderlich ist, kann die app .NET Framework 4.0, um dieses Verhalten abzurufen abzielen.|  
|Bereich|Kante|  
|Version|4.5.2|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|Analyzer|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: TargetFrameworkName für Standard-app-Domäne nicht mehr wird standardmäßig auf null, wenn nicht festgelegt  
  
|||  
|-|-|  
|Details|Die TargetFrameworkName wurde bereits in der Standardanwendungsdomäne null, sofern sie nicht explizit festgelegt wurde. 4.6 ab, müssen die TargetFrameworkName-Eigenschaft für die Standardanwendungsdomäne einen Standardwert (sofern vorhanden) die TargetFrameworkAttribute abgeleitet. Nicht standardmäßige Anwendungsdomänen weiterhin ihre TargetFrameworkName von der Standardanwendungsdomäne (die nicht auf null in 4.6 standardmäßig) erben, sofern sie nicht explizit überschrieben wird.|  
|Vorschlag|Code sollte aktualisiert werden, um nicht abhängig von `AppDomainSetup.TargetFrameworkName` mit dem Standardwert null. Wenn es erforderlich ist, dass diese Eigenschaft zu null ausgewertet weiterhin, es kann explizit festgelegt werden auf diesen Wert.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|Analyzer|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: X509Certificate2.ToString(bool) löst jetzt bei .NET das Zertifikat nicht verarbeiten kann  
  
|||  
|-|-|  
|Details|Zuvor diese Methode auslöst, wenn 'true' für den verbose-Parameter übergeben wurde und Zertifikate installiert sind, die von .net unterstützten waren nicht Framework. Nun wird die Methode erfolgreich ist und eine gültige Zeichenfolge zurück, die die nicht zugegriffen werden Teile der Certifiate lässt.|  
|Vorschlag|Code je nach X509Certificate2.ToString(bool) sollte aktualisiert werden, wenn Sie davon ausgehen, dass die zurückgegebene Zeichenfolge Zertifikatdaten (z. B. öffentliche Schlüssel, privaten Schlüssel und Erweiterungen) ausschließen kann in einigen Fällen in der API zuvor ausgelöst haben würde.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: Reflection-Objekte können nicht mehr von verwaltetem Code an Out-of-Process-DCOM-Clients übergeben werden  
  
|||  
|-|-|  
|Details|Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden. Die folgenden Typen sind betroffen:<br /><br /> Assembly<br /><br /> MemberInfo (und die abgeleiteten Typen, einschließlich FieldInfo, MethodInfo, Typ und TypeInfo)<br /><br /> MethodBody<br /><br /> Modul<br /><br /> ParameterInfo-Element.<br /><br /> Aufrufe von `IMarshal` für das Objekt zurückgeben `E_NOINTERFACE`.|  
|Vorschlag|Aktualisieren der Marshallingcode für die Arbeit mit nicht-Reflection-Objekte|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Laufzeit|  
|Analyzer|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition DateTimes gibt unterschiedliche Zeichenfolge zurück.  
  
|||  
|-|-|  
|Details|Zeichenfolgendarstellungen ContentDispositions wurden aktualisiert, 4.6, immer die Stundenkomponente des DateTime mit zwei Ziffern dargestellt ab. Dies ist zur Einhaltung [RFC822](http://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](http://www.ietf.org/rfc/rfc2822.txt). Dies bewirkt, dass `ContentDisposition.ToString` eine unterschiedliche Zeichenfolge in 4.6 in Szenarien, bei denen vor 10:00 Uhr war eines der Elemente für die Disposition Zeit zurückgegeben. Beachten Sie, dass ContentDispositions manchmal serialisiert werden, über die sie in Zeichenfolgen zu konvertieren, damit alle ContentDisposition ToString Operationen, Serialisierung oder GetHashCode Aufrufe geprüft werden müssen.|  
|Vorschlag|Erwarten Sie nicht, dass die zeichenfolgendarstellungen ContentDispositions aus verschiedenen Versionen von .NET Framework ordnungsgemäß miteinander verglichen werden soll. Konvertieren der Zeichenfolgen zurück, die ContentDispositions, wenn möglich, bevor Sie einen Vergleich durchführen.|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|Analyzer|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load nicht entfernen Symbol-Eigenschaft  
  
|||  
|-|-|  
|Details|Wenn .NET Framework 4.5 im Workflow-Designer, und Laden eine 3.5 neu gehosteten Workflow mit der Methode WorkflowDesigner.Load() abgezielt wird, wird eine XamlDuplicateMemberException beim Speichern des Workflows ausgelöst.|  
|Vorschlag|Dieser Fehler nur Manifeste, beim Abzielen auf .NET Framework 4.5 im Workflow-Designer, damit es durch Festlegen umgangen werden kann die `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` für .NET Framework 4.0.<br /><br /> Alternativ kann das Problem vermieden werden, mithilfe der [WorkflowContext.Load(string)](https://msdn.microsoft.com/en-us/library/ee425926\(v=vs.110\).aspx) -Methode zum Laden des Workflows, anstelle von [WorkflowDesigner.Load()](https://msdn.microsoft.com/en-us/library/ee403482\(v=vs.110\).aspx).|  
|Bereich|Hauptversion|  
|Version|4.5-4.5.2|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|Analyzer|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open schlägt unter Windows 7, mit nicht - IFS-Winsock BSP oder LSP vorhanden  
  
|||  
|-|-|  
|Details|SqlConneciton.Open und OpenAsync fehlschlagen in .NET Framework 4.5, wenn auf dem Computer vorhanden, die auf einer Windows 7-Computer mit einem nicht - IFS-Winsock BSP oder LSP ausgeführt sind.<br /><br /> Verwenden, um festzustellen, ob ein nicht - IFS BSP oder LSP installiert wird, die `netsh WinSock Show Catalog` Befehl aus, und untersuchen Sie alle `Winsock Catalog Provider Entry` Element, das zurückgegeben wird. Wenn der Wert des Flags-Dienst hat die `0x20000` Bit gesetzt, den Anbieter verwendet IFS-Handles und funktionieren ordnungsgemäß. Wenn die `0x20000` Bit deaktivieren (nicht festgelegt), wird ein nicht - IFS BSP oder LSP.|  
|Vorschlag|Dieses Problem behoben wurde in .NET Framework 4.5.2, damit es durch das Aktualisieren von .NET Framework vermieden werden kann. Alternativ kann es durch Entfernen alle installierten nicht - IFS Winsock-LSPs vermieden werden.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5.2|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|Analyzer|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84: implementiere "ICommand.CanExecuteChanged"-Ereignis Verhalten in .NET 4.5 geändert  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 wurde eine CanExecuteChangedEvent ignoriert, sei denn, der Absender des Ereignisses das gleiche Objekt wie das Objekt, das das Ereignis ausgelöst hat. Dieses Problem wurde in .NET Framework 4.5 Servcing Updates behoben.|  
|Vorschlag|Dieses Problem behoben wurde in .NET Framework 4.5 Versionen warten, damit dies vermieden werden kann, und sicherstellen, dass .NET Framework auf dem neuesten Stand ist oder durch ein Upgrade auf .NET Framework 4.5.1. Alternativ kann mit ICommand geändert werden, um sicherzustellen, dass der Sender beim Auslösen eines CanExecuteChanged-Befehls das Objekt, das das Ereignis auslöst identisch ist.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|Analyzer|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: Einige .NET APIs dazu führen, dass zuerst die Möglichkeit (behandelt) EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 eine kleine Anzahl .NET Methoden auslösen erste-Chance-EntryPointNotFoundExceptions wurde gestartet. Diese Ausnahmen behandelt wurden, in der .net Framework jedoch ausfallen Automatisierung, die nicht die Ausnahmen (ersten Chance) erwartet. Derselben APIs unterbrechen Szenarien ApiVerifier, wenn HighVersionLie aktiviert ist.|  
|Vorschlag|Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ kann nicht auf der ersten Chance EntryPointNotFoundExceptions unterbrechen Automatisierung aktualisiert werden.|  
|Bereich|Kante|  
|Version|4.5-4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> [Debug.Assert-Methode (boolesch, Zeichenfolge, Objekt\<xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|Analyzer|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: Hängenbleiben führen einen Bildlauf ein WPF-Strukturansicht oder gruppierten ListBox in einem VirtualizingStackPanel  
  
|||  
|-|-|  
|Details|In der .NET Framework&4;.5 kann Bildlauf TreeView WPF in einer virtualisierten StackPanel-Element hängt verursachen, wenn Ränder im Viewport (zwischen den Elementen, die in der Strukturansicht oder auf einem ItemsPresenter-Element). Darüber hinaus können in einigen Fällen unterschiedliche Größe Elemente in der Ansicht instabil werden auch wenn keine Seitenränder.|  
|Vorschlag|Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ können Ränder aus Sicht Sammlungen (z. B. TreeViews) im virtualisierten StackPanels entfernt werden, wenn alle enthaltenen Elemente über die gleiche Größe aufweisen.|  
|Bereich|Hauptversion|  
|Version|4.5-4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom gibt falsche Ergebnis für generische Variablen mit Einschränkungen  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 Type.IsAssignableFrom wird falsch zurückgegeben `false` in allen Fällen für einige generischen Typen mit Einschränkungen.|  
|Vorschlag|Dieses Problem wurde in einem-Wartungsupdate behoben. Aktualisieren Sie .NET Framework 4.5 oder ein Upgrade auf .NET Framework 4.5.1 oder höher, um dieses Problem zu beheben. Alternativ können vermeiden Sie IsAssignableFrom mit generischen Typen, die Einschränkungen für generische Parameter aufweisen. Reflektions-APIs können als eine Umgehung verwendet werden.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|Analyzer|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: Entity Framework 6.0 wird in apps, die von Visual Studio gestartet sehr langsam geladen.  
  
|||  
|-|-|  
|Details|Starten einer Anwendung von Visual Studio 2013, die mithilfe von Entity Framework 6.0 kann sehr langsam sein.|  
|Vorschlag|Dieses Problem wurde in Entity Framework 6.0.2 behoben. Aktualisieren Sie Entity Framework, um Leistungsprobleme zu vermeiden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: mehrzeiligen ASP.Net Textfeld Abstand geändert werden soll, wenn AntiXSSEncoder verwenden  
  
|||  
|-|-|  
|Details|In .NET Framework 4.0, zusätzliche Zeilen eingefügt wurden zwischen den Zeilen eines mehrzeiligen Textfeldes beim Postback bei Verwendung der `AntiXSSEncoder`. In .NET Framework 4.5 sind diese zusätzlichen Zeilenumbrüche nicht enthalten, aber nur, wenn die Web-app auf .NET 4.5|  
|Vorschlag|Bedenken Sie, dass 4.0 Web-apps, die auf .NET 4.5 fehlgeleitet mehrzeiligen Textfeldern verbessert, um mehr zusätzliche Zeilenumbrüche eingefügt haben. Wenn dies nicht erwünscht ist, kann die Anwendung das alte Verhalten ist in .NET Framework 4.5 ausgeführt wird als Ziel .NET Framework 4.0.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Analyzer|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue<>\>. TryPeek kann über die Out-Parameter eine fehlerhafte Null zurückgeben.  
  
|||  
|-|-|  
|Details|In einigen Szenarien mit mehreren Threads `ConcurentQueue<T>.TryPeek` "true" zurückgeben können, aber den Out-Parameter mit einem Nullwert (anstelle der richtigen, eingesehenen-Wert) aufgefüllt.|  
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.1 behoben. Aktualisieren auf dieses Framework wird das Problem behoben.|  
|Bereich|Hauptversion|  
|Version|4.5-4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|Analyzer|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: mehrere Elemente in einer einzelnen TableLayoutPanel-Zelle können neu angeordnet werden  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 Wenn mehrere Elemente in der gleichen TableLayoutPanel-Zelle platziert werden können sie in einer anderen Reihenfolge angezeigt werden als in .NET Framework 4.0 wurden.|  
|Vorschlag|Dieses Verhalten wurde in einem Dienst Update für .NET Framework 4.5 zurückgesetzt. Aktualisieren Sie .NET Framework 4.5 oder ein Upgrade auf .NET Framework 4.5.1 oder höher, um dieses Problem zu beheben. Vermeiden Sie, den mehrdeutigen Fall mehrerer Elemente in der gleichen TableLayourPanel Zelle.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analyzer|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: Iteratorvariablen Foreach ist jetzt in der Iteration beschränkt, damit Closure erfasst Semantik (in C#&5;) unterscheiden  
  
|||  
|-|-|  
|Details|Foreach-Iteratorvariablen c# 5 (Visual Studio 2012) ab, in der Iteration beschränkt. Dies kann Seitenumbrüche verursachen, wenn Code zuvor auf die Variablen, die nicht in der Foreach-Closure aufgenommen wurde. Das Symptom dieser Änderung werden, dass eine Iteratorvariable an eine Delagate übergeben als Wert behandelt werden, der zum Zeitpunkt der Erstellung des Delegaten, anstelle des Wertes, der zum Zeitpunkt, wenn der Delegat aufgerufen wurde.|  
|Vorschlag|Im Idealfall sollte Code aktualisiert werden, um die neuen Compilerverhalten zu erwarten. Wenn die alten Semantik erforderlich sind, kann die Iteratorvariable mit einer separaten Variablen ersetzt werden die explizit außerhalb der Schleife Bereich platziert wird.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Analyzer|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter wird nicht gerendert.\`<br>\>' Element ordnungsgemäß  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.6 Aufrufen `HtmlTextWriter.RenderBeginTag()` und `HtmlTextWriter.RenderEndTag()` mit einem `<BR />` Element ordnungsgemäß einzufügen, nur eine `<BR />` (statt zwei)|  
|Vorschlag|Wenn eine Anwendung auf die zusätzlichen abhängigen `<BR />` Tag `HtmlTextWriter.RenderBeginTag()` ein zweites Mal aufgerufen werden soll. Beachten Sie, das dieses Verhalten ändern, wirkt sich nur apps, die .NET Framework 4.6 als Ziel verwenden, können Sie eine frühere Version von .NET Framework abzielen, um das alte Verhalten abzurufen.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|Analyzer|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: Aufrufen von Items.Refresh auf einer WPF-ListBox, ListView oder DataGrid mit der ausgewählten Elemente können dazu führen, dass doppelte Elemente in das Element angezeigt werden  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 kann ListBox.Items.Refresh vom Code aufrufen, während Elemente in einem Listenfeld ausgewählt sind die ausgewählten Elemente in der Liste dupliziert werden. Ein ähnliches Problem tritt auf, mit dem ListView-Steuerelement und dem DataGrid. Dies ist in .NET Framework 4.6 behoben.|  
|Vorschlag|Dieses Problem kann umgangen werden, indem Elemente programmgesteuert fest, bevor, Aktualisieren aufgerufen wird und anschließend erneut sie nach Abschluss des Aufrufs. Alternativ können Sie dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework adressiert werden.|  
|Bereich|Nebenversion|  
|Version|4.5-4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|Analyzer|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: EventListeners ETW-Ereignisse von Anbietern mit expliziten Schlüsselwörter (z. B. die TPL-Anbieter) nicht erfassen  
  
|||  
|-|-|  
|Details|Ereignisse von Anbietern mit expliziten Schlüsselwörter erfassen ETW-EventListeners mit einer leeren Schlüsselwortmaske nicht ordnungsgemäß. In .NET Framework 4.5 der Anbieter TPL begann explizite Schlüsselwörter bereitstellen und die dieses Problem ausgelöst. In .NET Framework 4.6 wurden EventListeners aktualisiert, damit dieses Problem nicht mehr vorhanden.|  
|Vorschlag|Um dieses Problem zu umgehen, ersetzen Sie Aufrufe EnableEvents (EventSource Level) durch Aufrufe an die EnableEvents-Überladung, die explizit, die Maske "Schlüsselwörter angibt" verwenden: `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`.<br /><br /> Alternativ können Sie dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework adressiert werden.|  
|Bereich|Kante|  
|Version|4.5-4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|Analyzer|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: Erstellen von Entity Framework Edmx mit Visual Studio 2013 kann tritt der Fehler MSB4062 bei Verwendung der EntityDeploySplit oder EntityClean-Aufgaben  
  
|||  
|-|-|  
|Details|MSBuild 12.0-Tools (enthalten in Visual Studio 2013) geändert Msbuild Speicherorte ungültig werden ältere Entity Framework-Targets-Dateien verursacht. Das Ergebnis ist, `EntityDeploySplit` und `EntityClean` Tasks schlagen fehl, da sie nicht gefunden werden `Microsoft.Data.Entity.Build.Tasks.dll`. Beachten Sie, dass diese Unterbrechung aufgrund einer Änderung Toolset (Msbuild/VS) nicht aufgrund einer Änderung des .NET Framework. Es tritt nur beim Entwicklertools, nicht beim Aktualisieren von .NET Framework nur.|  
|Vorschlag|Entity Framework Targets-Dateien werden für die Arbeit mit dem neuen Msbuild Layout Anfang in .NET Framework 4.6 behoben. Upgrade auf diese Version von Framework wird dieses Problem beheben. Sie können auch [dies](http://stackoverflow.com/a/24249247/131944) Abhilfe kann verwendet werden, um Targets-Dateien direkt zu patchen.|  
|Bereich|Hauptversion|  
|Version|4.5.1-4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: jetzt XSD-Schema-Validation Verstöße gegen unique-Einschränkungen ordnungsgemäß erkannt wird, wenn zusammengesetzte Schlüssel verwendet werden und ein Schlüssel leer ist  
  
|||  
|-|-|  
|Details|Versionen von .NET Framework vor 4.6 hat einen Fehler, der verursacht XSD-Validierung unique-Einschränkungen für zusammengesetzte Schlüssel nicht erkennen, wenn eine der Tasten leer war. In .NET Framework 4.6 wird dieses Problem behoben. Dies führt zu mehr einwandfreie Prüfung, aber möglicherweise auch in einigen XML-Überprüfung der zuvor hätte.|  
|Vorschlag|Wenn großzügiger, .NET Framework 4.0-Überprüfung erforderlich ist, die Anwendung überprüfen kann als Ziel Version 4.5 (oder früher) von .NET Framework. Wenn für .NET 4.6 erneutem Anzielen, jedoch sollten Überprüfung des Codes durchgeführt werden, um sicherzustellen, dass doppelte zusammengesetzten Schlüssel (wie in der Beschreibung des Problems beschrieben) nicht erwartet werden, um zu überprüfen.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: Aufruf Attribute.GetCustomAttributes auf eine Indexereigenschaft AmbiguousMatchException mehr wird ausgelöst, wenn die Mehrdeutigkeit durch den Typ des Indexes aufgelöst werden kann  
  
|||  
|-|-|  
|Details|Vor dem Aufrufen von .NET Framework 4.6 `GetCustomAttribute(s)` für einen Indexer-Eigenschaft die von einer anderen Eigenschaft nur durch den Typ des Indexes beinhalteten ergibt ein `AmbiguousMatchException`. Ab .NET Framework 4.6 werden die Eigenschaft Attribute ordnungsgemäß zurückgegeben werden.|  
|Vorschlag|Bedenken Sie, dass GetCustomAttribute(s) häufiger nun funktioniert. Wenn eine app auf zuvor verlassen wurde der `AmbiguousMatchException`, Reflektion sollte jetzt verwendet werden, um explizit für mehrere Indexer stattdessen suchen.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: Führen Sie einen Bildlauf zum unteren Element in ItemsControl-Steuerelemente (z. B. ListBox und DataGrid) zeitweise nicht bei Verwendung von benutzerdefinierten DataTemplates  
  
|||  
|-|-|  
|Details|In einigen Fällen verursacht ein Fehler in .NET Framework 4.5 ItemsControl-Steuerelemente (z. B. ListBox, ComboBox, DataGrid usw.), nicht einen Bildlauf zu ihren jeweiligen unten bei Verwendung von benutzerdefinierten DataTemplates. Wenn der Bildlauf ein zweites Mal (bei einem Bildlauf nach sichern) versucht wird, funktioniert dann.|  
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.2 behoben und kann durch ein Upgrade auf diese Version (oder eine höhere Version) von .NET Framework behandelt werden. Alternativ können Sie Benutzer können weiterhin auf die endgültige Elemente in diesen Auflistungen ziehen, Bildlaufleisten, aber möglicherweise zweimal dies versuchen erfolgreich.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5.2|  
|Typ|Laufzeit|  
|Analyzer|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: GlyphRun.ComputeInkBoundingBox() und FormattedText.Extent Geben Sie andere Werte, die ab .NET 4.5 zurück.  
  
|||  
|-|-|  
|Details|Verbesserungen wurden vorgenommen, GlyphRun.ComputeInkBoundingBox() und FormattedText.Extent in .NET Framework 4.5 um Probleme zu beheben, in denen die Felder, die zu klein für die darin enthaltenen Symbole in einigen Fällen in .NET Framework 4.0 wurden. Dadurch werden einige Begrenzungsrahmen größere ab .NET Framework 4.5, sodass geringfügige Unterschiede in der UI-Layout.|  
|Vorschlag|Bedenken Sie, dass einige Symbol umgebende Feld Größe angewachsen ist. Diese Änderungen werden in der Regel verbessert, Präsentation und Treffer Feld testen, aber wenn das ältere (vor .NET 4.5)-Verhalten gewünscht wird, sie können werden teilgenommen durch den folgenden Eintrag zur app.config-Datei hinzufügen:<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|Analyzer|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: Aufrufen von DataGrid.CommitEdit von einem CellEditEnding-Handler löscht den Fokus  
  
|||  
|-|-|  
|Details|Löst ein Aufruf von DataGrid.CommitEdit aus einem Ereignishandler für das DataGrid CellEditEnding DataGrid den Fokus verliert.|  
|Vorschlag|Dieses Problem behoben wurde in .NET Framework 4.5.2, damit es durch das Aktualisieren von .NET Framework vermieden werden kann. Alternativ kann es dazu explizit erneut DataGrid nach dem Aufruf von CommitEdit vermieden werden.|  
|Bereich|Kante|  
|Version|4.5-4.5.2|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über die Routenparameter übergeben  
  
|||  
|-|-|  
|Details|Um RFC 2396 entsprechen, werden Leerzeichen in Pfaden Route jetzt mit Escapezeichen versehen beim Auffüllen der Action-Parameter aus einer Route. Daher während `/controller/action/some data` entsprechen zuvor die Route `/controller/action/{data}` und `some data` als Datenparameter erhalten sie jetzt `some%20data` stattdessen.|  
|Vorschlag|Code muss aktualisiert werden, um die unescape-Parameter für eine Route. Wird der ursprüngliche URI benötigt, kann er mit der Request.RequestUri.OriginalString-API zugegriffen werden.|  
|Bereich|Nebenversion|  
|Version|4.5.2|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Web.Http.RouteAttribute.%23ctor%28System.String%29?displayProperty=fullName>|  
|Analyzer|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET Kennzeichnung durch einen Namespace teilweise nicht mehr für System.Windows-APIs unterstützt  
  
|||  
|-|-|  
|Details|Ab .NET 4.5.2, können nicht VB.NET-Projekten System.Windows-APIs mit teilweise qualifizierte Namespaces angeben. Beispielsweise verweisen auf `Windows.Forms.DialogResult` fehl. Stattdessen muss Code finden Sie in den vollqualifizierten Namen (`System.Windows.Forms.DialogResult`) oder bestimmten Namespace zu importieren und verweisen Sie einfach zu `DialogResult`.|  
|Vorschlag|Code sollte aktualisiert werden, um auf verweisen `System.Windows` APIs mit einfachen Namen (und den entsprechenden Namespace importiert) oder mit den voll qualifizierten Namen.|  
|Bereich|Nebenversion|  
|Version|4.5.2|  
|Typ|Neuzuweisung|  
|Analyzer|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: bidirektionale Datenbindung an eine Eigenschaft mit einem nicht öffentlichen Setter wird nicht unterstützt.  
  
|||  
|-|-|  
|Details|So binden Sie Daten an eine Eigenschaft ohne einen öffentlichen Setter Versuch war noch nie ein unterstütztes Szenario. Ab .NET Framework 4.5.1, wird dieses Szenario eine InvalidOperationException ausgelöst. Beachten Sie, dass diese neue Ausnahme nur für apps ausgelöst wird, die speziell .NET Framework 4.5.1 abzielen. Wenn eine app .NET Framework 4.5 ausgerichtet ist, wird der Aufruf zugelassen werden. Wenn die app keine bestimmte Version von .NET Framework zum Ziel hat, wird die Bindung als unidirektionaler behandelt.|  
|Vorschlag|Die app sollte aktualisiert werden, um unidirektionale Bindung verwenden, oder öffentlich verfügbar machen Setter der Eigenschaft. Alternativ können Sie bewirkt als Ziel .NET Framework 4.5 die app auf das alte Verhalten.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|Analyzer|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Marshal.SizeOf und Marshal.PtrToStructure Überladungen Break dynamischem Code  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5.1, Dynamisches Binden von den Methoden `Marshal.SizeOf` oder `Marshal.PtrToStructure` (über Windows PowerShell, IronPython und das C#-dynamic-Schlüsselwort, z. B.) kann dazu führen, dass `MethodInvocationExceptions` da neue Überladungen dieser Methoden, die möglicherweise die Skriptmodule mehrdeutig hinzugefügt wurden.|  
|Vorschlag|Aktualisieren von Skripts, um klar anzugeben, welche Überladung muss ein verwendet. Dies erfolgt durch die Methoden Typparameter als explizit umwandeln kann `System.Type`. Finden Sie unter [diesen Link](https://support.microsoft.com/en-us/kb/2909958/) für weitere Details und Beispiele zur Umgehung des Problems.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Analyzer|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: PreviewLostKeyboardFocus wird wiederholt aufgerufen, wenn der Handler ein Windows Forms-Meldungsfeld angezeigt wird.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5, Aufrufen `System.Windows.Forms.MessageBox.Show` aus einem `UIElement.PreviewLostKeyboardFocus` Handler führt dazu, dass den Handler erneut ausgelöst, wenn das Meldungsfeld geschlossen wird, was ggf. in einer Endlosschleife Meldungsfelder.|  
|Vorschlag|Es gibt zwei Optionen zum Umgehen dieses Problems-<br /><br /> Es vermieden werden kann, durch Aufrufen von `System.Windows.MessageBox.Show` anstelle von `System.Windows.Forms.MessageBox.Show`.<br /><br /> Kann vermieden werden, indem das Meldungsfeld aus Anzeigen einer `LostKeyboardFocus` -Ereignishandler (im Gegensatz zu einer `PreviewLostKeyboardFocus` -Ereignishandler).|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|Analyzer|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: eine Serialisierung in .NET 4.5 mit NetDataContractSerializer ConcurrentDictionary kann nicht deserialisiert werden, von .NET 4.5.1 oder 4.5.2  
  
|||  
|-|-|  
|Details|Aufgrund von internen Änderungen in den Typ `System.Collections.Concurrent.ConcurrentDictionary` Objekte, die mit .NET Framework 4.5 serialisiert werden mithilfe der `NetDataContractSerializer` kann nicht deserialisiert werden, in .NET Framework 4.5.1 oder in .NET Framework 4.5.2.<br /><br /> Beachten Sie, dass durch das Verschieben der anderen Richtung (mit .NET Framework serialisieren 4.5.x und Deserialisieren von .NET Framework 4.5) funktioniert. Auf ähnliche Weise funktioniert 4.x versionsübergreifende Serialisierung mit .NET Framework 4.6.<br /><br /> Serialisierung und Deserialisierung mit einer einzigen Version von .NET Framework ist nicht betroffen.|  
|Vorschlag|Wenn es zum Serialisieren und Deserialisieren von einem ConcurrentDictionary zwischen .NET Framework 4.5 und .NET Framework 4.5.1/4.5.2 notwendig ist, sollte ein alternatives Serialisierungsprogramm wie das Serialisierungsprogramm DataContractSerializer oder BinaryFormatter anstelle NetDataContractSerializer verwendet werden.<br /><br /> Alternativ können Sie da dieses Problem in .NET Framework 4.6 behandelt wird, kann es gelöst werden durch ein Upgrade auf diese Version von .NET Framework.|  
|Bereich|Nebenversion|  
|Version|4.5.1-4.6|  
|Typ|Laufzeit|  
|Analyzer|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: persischen Kalender verwendet jetzt den Hijri-solaralgorithmus  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.6, verwendet die persischen Kalenders-Klasse der Hijri-solaralgorithmus. Konvertieren von Daten zwischen des persischen Kalenders und anderen Kalender erzeugt möglicherweise eine etwas anderes Ergebnis mit .NET Framework 4.6 für Datumsangaben vor 1800 oder später als 2023 (gregorianischen) beginnt.<br /><br /> Darüber hinaus `PersianCalendar.MinSupportedDateTime` ist jetzt `March 22, 0622 instead of March 21, 0622`.|  
|Vorschlag|Denken Sie daran, dass einige Daten früheren oder späten möglicherweise geringfügig, wenn mithilfe des persischen Kalenders in .NET 4.6. Auch beim Serialisieren von Daten zwischen Prozessen, die auf verschiedenen Versionen von .NET Framework ausgeführt werden kann speichern Sie sie als persischen Kalenders Datumszeichenfolgen (da diese Werte unterscheiden können).|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|Analyzer|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: Aufrufen von CreateDefaultAuthorizationContext mit einem null-Argument wurde geändert.  
  
|||  
|-|-|  
|Details|Die Implementierung von AuthorizationContext zurückgegeben wird, durch einen Aufruf der `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` mit einer null AuthorizationPolicies Argument seine Implementierung in .NET Framework 4.6 geändert hat.|  
|Vorschlag|In seltenen Fällen liegen bei WCF-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor. In solchen Fällen kann das vorherige Verhalten auf zwei Arten wiederhergestellt werden:<br /><br /> Kompilieren Sie Ihre App erneut, damit sie auf eine frühere Version als .NET Framework 4.6 abzielt. Für IIS-gehostete Dienste verwenden die <httpRuntime targetframework="x.x"></httpRuntime> \> Element auf eine frühere Version von .NET Framework abzielen.<br /><br /> Fügen Sie die folgende Zeile in die `<appSettings>` Abschnitt der Datei "App.config":`<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|Analyzer|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: WPF TreeViewItem werden in einem TreeView-Steuerelement verwendet werden  
  
|||  
|-|-|  
|Details|Eine Änderung wurde eingeführt, 4.5, die Verwendung von TreeViewItem-Elementen außerhalb von TreeView beschränkt. Dies äußert sich in den folgenden Situationen:<br /><br /> Die TreeViewItem visual übergeordnete ist ein Panel. (Für TreeView generiert TreeViewItem weist einen Bereich als übergeordnetes Element)<br /><br /> Die TreeViewItem ist ein Nachfolger ein VirtualizingStackPanel als "ElementHost" für ein Listenfeld-Steuerelement (ListBox, DataGrid, ListView, etc.). Virtualisierung muss aktiviert sein.<br /><br /> Die VirtualizingStackPanel ist Element Bildlauf (`ScrollUnit="Item"`).<br /><br /> Jemand ruft `VirtualizingStackPanel.MakeVisible(v)` ein Element navigieren `v` angezeigt. Dies kann explizit oder implizit in verschiedene Arten erfolgen; vielleicht die am häufigsten verwendeten Weise wird einfach durch Klicken auf `v` damit es den Tastaturfokus erhält.<br /><br /> Der visuelle-übergeordnete Kette von `v` an die VirtualizingStackPanel durchläuft die TreeViewItem-Elements.<br /><br /> Das heißt, wird dies beim ein TreeViewItem-Elements außerhalb von TreeView verwendet wird, und der Benutzer auf ein Nachfolger der TreeViewItem klickt, um es sichtbar zu machen angezeigt. Wenn die TreeViewItem den Fokus erhalten kann keine abhängigen Elemente verfügt, sehen Sie nie dieses Problem. Ein Beispiel für eine Situation, in denen dies erreicht wird, wird ein TreeViewItem-Elements von einem DataTemplate ist.  Wenn dieses Problem erreicht wird, besteht eine InvalidCastException-Ausnahme, die innerhalb der WPF-Framework auftritt.|  
|Vorschlag|Ein Hotfix wird für diesen verfügbar gemacht werden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims berücksichtigt alle ClaimTypes (Anspruchstypen)  
  
|||  
|-|-|  
|Details|In apps versucht für .NET Framework 4.6.1, wenn ein Satz von Ansprüchen aus einem Zertifikat initialisiert wird, die mehrere DNS-Einträge in das Feld SAN X509 FindClaims-Methode der ClaimType-Argument mit der DNS-Einträge entsprechend.<br /><br /> Die FindClaims-Methode versucht, für apps, die frühere Versionen von .NET Framework abzielen, das Argument ClaimType nur mit der letzten DNS-Eintrag entspricht.|  
|Vorschlag|Diese Änderung wirkt sich nur für .NET Framework 4.6.1 Applications. Diese Änderung kann deaktiviert werden (oder aktiviert, wenn als Ziel Pre-4.6.1) mit der [DisableMultipleDNSEntries](https://msdn.microsoft.com/en-us/library/mt620030%28v=vs.110%29.aspx) Kompatibilitätsschalter.|  
|Bereich|Nebenversion|  
|Version|4.6.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|Analyzer|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage löst nicht mehr für eintrittsinvariant Implementierungen von IMessageFilter.PreFilterMessage  
  
|||  
|-|-|  
|Details|Vor .NET Framework 4.6.1 Aufrufen von Application.FilterMessage mit einer IMessageFilter.PreFilterMessage die aufgerufene AddMessageFilter oder RemoveMessageFilter (beim Aufrufen von auch Application.DoEvents) IndexOutOfRangeException würde.<br /><br /> Beginnen mit dem .NET Framework 4.6.1, wird diese Ausnahme nicht mehr ausgelöst, und eintrittsinvariant Filter wie oben beschrieben können verwendet werden.|  
|Vorschlag|Bedenken Sie, dass Application.FilterMessage nicht mehr für das oben beschriebene eintrittsinvariant IMessageFilter.PreFilterMessage Verhalten ausgelöst wird. Dies gilt nur für .NET Framework 4.6.1 Applications.<br /><br /> Apps für .NET Framework 4.6.1 können ablehnen dieser Änderung (oder apps, die mit älteren Frameworks teilnehmen können) mithilfe der [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/en-us/library/mt620032%28v=vs.110%29.aspx) Kompatibilitätsschalter.|  
|Bereich|Kante|  
|Version|4.6.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|Analyzer|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture wird in WPF-Dispatcher-Vorgänge nicht beibehalten  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.6 CurrentCulture und CurrentUICulture Änderungen innerhalb einer [Dispatcher](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx) am Ende dieses Vorgangs Dispatcher verloren. Auf ähnliche Weise können CurrentCulture und CurrentUICulture außerhalb der Dispatcher-Vorgang nicht wenn entsprechend geändert werden, dass der Vorgang ausgeführt wird.<br /><br /> Praktisch gesehen bedeutet dies, dass CurrentCulture und CurrentUICulture Änderungen zwischen WPF UI-Rückrufe und anderen Code in einer WPF-Anwendung weitergeben können.<br /><br /> Dies ist aufgrund einer Änderung in [ExecutionContext](https://msdn.microsoft.com/en-us/library/system.threading.executioncontext%28v=vs.110%29.aspx) , die bewirkt, dass CurrentCulture und CurrentUICulture in den Kontext beginnend mit apps für .NET Framework 4.6 gespeichert werden. WPF-Dispatcher Vorgänge speichern den Ausführungskontext verwendet, um den Vorgang zu beginnen und den vorherigen Kontext wiederherstellen, wenn der Vorgang abgeschlossen ist. Da CurrentCulture und CurrentUICulture jetzt Bestandteil dieses Kontexts sind, werden die Änderungen werden in ein Dispatcher-Vorgang außerhalb der Vorgang nicht beibehalten.|  
|Vorschlag|Apps, die von dieser Änderung betroffen möglicherweise umgehen, indem die gewünschten CurrentCulture speichern oder CurrentUICulture in einem Feld und alle Verteiler Vorgang Einchecken stellen (einschließlich UI-Rückruf Ereignishandler), dass die richtigen CurrentCulture und CurrentUICulture festgelegt sind. Alternativ wird da ExecutionContext ändern zugrunde liegenden WPF Änderung betrifft nur apps, die für das .NET Framework, Version 4.6 oder höher, diese Unterbrechung kann vermieden werden, indem für das .NET Framework 4.5.2.|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0145|
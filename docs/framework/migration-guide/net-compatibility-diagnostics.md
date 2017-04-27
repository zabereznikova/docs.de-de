---
title: "Diagnose der .NET-Kompatibilität | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: twsouthwick
ms.author: tasou
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 06ebf87e02c8fd745d9c2f3a55eca329323a7d91
ms.lasthandoff: 04/18/2017

---
# <a name="net-compatibility-diagnostics"></a>Diagnose der .NET-Kompatibilität
Die Diagnose der .NET Kompatibilität umfasst von Roslyn unterstützte Analyzer, die bei der Erkennung von Anwendungskompatibilitätsproblemen zwischen .NET Framework-Versionen helfen. Diese Liste enthält alle verfügbaren Analyzer, obwohl nur eine Teilmenge auf eine bestimmte Migration angewendet werden kann. Die Analyzer ermitteln, welche Probleme auf die geplante Migration zutreffen und beschreibt diese nur kurz. Probleme, die nach den betroffenen Versionen unterteilt sind, finden Sie unter [Anwendungskompatibilität](../../../docs/framework/migration-guide/application-compatibility.md).  
  
 Jedes Problem umfasst die folgenden Informationen:  
  
-   Die Beschreibung der Änderungen von einer früheren Version.  
  
-   Die Empfehlung ist eine Beschreibung, wie sich die Änderung auf Kunden auswirkt und ob Problemumgehungen verfügbar sind, um die Kompatibilität zwischen Versionen beizubehalten.  
  
-   Eine Bewertung der Bedeutung der Änderung. Anwendungskompatibilitätsprobleme werden wie folgt kategorisiert:  
  
    |||  
    |-|-|  
    |Hauptversion|Eine wesentliche Änderung, die eine große Anzahl von Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht.|  
    |Nebenversion|Eine Änderung, die eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.|  
    |Grenzfall|Eine Änderung, die nur Apps in sehr spezifischen, nicht üblichen Szenarien beeinflusst.|  
    |Transparent|Eine Änderung ohne nennenswerte Auswirkungen auf die Entwickler oder Benutzer der Anwendung.|  
  
-   Die Version gibt an, wann die Änderung zum ersten Mal im Framework auftritt. Einige der Änderungen wurden rückgängig gemacht und das wird ebenfalls angegeben.  
  
-   Art der Änderung:  
  
    |||  
    |-|-|  
    |Neuzuweisung|Die Änderung wirkt sich auf Apps aus, die neu kompiliert werden, um auf eine neue Version von .NET Framework ausgerichtet zu werden.|  
    |Laufzeit|Die Änderung wirkt sich auf eine vorhandene Anwendung aus, die auf eine frühere Version von .NET Framework ausgerichtet ist, aber unter einer höheren Version ausgeführt wird.|  
  
-   Die betroffenen APIs, falls vorhanden.  
  
-   Die IDs der verfügbaren Diagnosen.  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: Hashtable und ähnlich sortierte Auflistungsobjekte können von SoapFormatter nicht deserialisiert werden.  
  
|||  
|-|-|  
|Details|SoapFormatter garantiert nicht dafür, dass unter einer .NET Framework-Version serialisierte Objekte erfolgreich unter einen anderen Version deserialisiert werden können. Insbesondere einige sortierte Auflistungen (z. B. Hashtable) haben Member zwischen 4.0 und 4.5 hinzugefügt, sodass Objekte dieser Typen nicht mit .NET 4.0 deserialisiert werden können, wenn sie mit .NET 4.5 serialisiert wurden. Beachten Sie, dass kein Problem auftritt, wenn die serialisierten Daten mit derselben Version von .NET Framework sowohl serialisiert als auch deserialisiert werden.|  
|Vorschlag|Die SoapFormatter-Serialisierung sollte durch die BinaryFormatter-Serialisierung oder „NetDataContractSerialization“ ersetzt werden, um in Bezug auf .NET Framework-Änderungen flexibel zu sein.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|Analyzer|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: WPF DataTemplate-Elemente sind jetzt für die UIA sichtbar.  
  
|||  
|-|-|  
|Details|Früher waren DataTemplate-Elemente für die Benutzeroberflächenautomatisierung nicht sichtbar. Ab Version 4.5 erkennt die Benutzeroberflächenautomatisierung diese Elemente. Dies ist in vielen Fällen hilfreich, kann aber bei Tests zu Problemen führen, die von UIA-Strukturen abhängen, die keine DataTemplate-Elemente enthalten.|  
|Vorschlag|Tests für die Benutzeroberflächenautomatisierung für diese App müssen möglicherweise aktualisiert werden, um die UIA-Struktur zu berücksichtigen, die jetzt zuvor unsichtbare DataTemplate-Elemente enthält. Beispielsweise müssen Tests, die erwarten, dass einige Elemente nebeneinander angeordnet sind, jetzt möglicherweise davon ausgehen, dass sich zwischen diesen Elementen zuvor unsichtbare UIA-Elemente befinden. Möglicherweise müssen auch Tests mit neuen Werten aktualisiert werden, die auf bestimmte Werte oder Indizes für UIA-Elemente angewiesen sind.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|Analyzer|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: In einem WPF TextBox markierter Text wird in einer anderen Farbe angezeigt, wenn das Textfeld inaktiv ist.  
  
|||  
|-|-|  
|Details|Wenn in .NET 4.5 ein WPF-Textfeldsteuerelement inaktiv ist (nicht den Fokus besitzt), wird der im Feld markierte Text in einer anderen Farbe als bei einem aktiven Steuerelement angezeigt.|  
|Vorschlag|Das vorherige (.NET 4.0) Verhalten kann wiederhergestellt werden, indem für die [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx)-Eigenschaft der Wert „false“ festgelegt wird.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analyzer|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List\<T>.ForEach kann beim Ändern eines Listenelements eine Ausnahme auslösen.  
  
|||  
|-|-|  
|Details|Ab .NET 4.5 löst ein `List<T>.ForEach`-Enumerator eine InvalidOperationException-Ausnahme aus, wenn ein Element in der aufrufenden Auflistung geändert wird. Zuvor hätte dies keine Ausnahme ausgelöst, aber zu Racebedingungen geführt.|  
|Vorschlag|Im Idealfall sollte der Code unveränderlich sein, damit Listen nicht geändert werden, während ihre Elemente aufgezählt werden, da dies nie ein sicherer Vorgang ist. Eine App kann auf .NET 4.0 ausgerichtet werden, um zum vorherigen Verhalten zurückzukehren.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|Analyzer|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: Die System.Uri-Analyse entspricht RFC 3987.  
  
|||  
|-|-|  
|Details|Die URI-Analyse hat sich seit .NET 4.5 auf verschiedene Weise geändert. Beachten Sie jedoch, dass sich diese Änderungen nur auf Code auswirken, der auf .NET 4.5 ausgerichtet ist. Wenn eine Binärdatei auf .NET 4.0 ausgerichtet ist, wird das alte Verhalten beobachtet. Die Änderungen an der URI-Analyse in .NET 4.5 umfassen Folgendes:<br /><br /> Die URI-Analyse führen die Normalisierung und Zeichenüberprüfung gemäß den neuesten IRI-Regeln in RFC 3987 aus.<br /><br /> Die Unicode-Normalisierungsform C wird nur für den Hostteil des URIs ausgeführt.<br /><br /> Ungültiges „mailto“: URIs lösen jetzt eine Ausnahme aus.<br /><br /> Nachgestellte Punkte am Ende eines Pfadsegments bleiben jetzt erhalten.<br /><br /> `file://`-URIs versehen das `?`-Zeichen nicht mit Escapezeichen.<br /><br /> Unicode-Steuerzeichen `U+0080` bis `U+009F` werden nicht unterstützt.<br /><br /> Für Kommas `,` oder `%2c` wird das Escapezeichen nicht automatisch entfernt.|  
|Vorschlag|Wenn die alte Semantik der .NET 4.0-URI-Analyse erforderlich ist (das ist nicht häufig der Fall), kann sie durch die Ausrichtung auf .NET 4.0 verwendet werden. Dies kann mithilfe von „TargetFrameworkAttribute“ für die Assembly oder  auf der Seite „Projekteigenschaften“ über die Benutzeroberfläche des Projektsystems von Visual Studio erreicht werden.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|Analyzer|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: System.Uri-Escapezeichen unterstützen jetzt RFC 3986 (http://tools.ietf.org/html/rfc3986).  
  
|||  
|-|-|  
|Details|URI-Escapezeichen in .NET 4.5 wurden geändert, um [RFC 3986](http://tools.ietf.org/html/rfc3986) zu unterstützen. Die speziellen Änderungen umfassen Folgendes:<br /><br /> `EscapeDataString` versieht reservierte Zeichen basierend auf RFC 3986 mit Escapezeichen.<br /><br /> `EscapeUriString` versieht reservierte Zeichen nicht mit Escapezeichen.<br /><br /> `UnescapeDataString` löst keine Ausnahme aus, wenn eine ungültige Escapesequenz gefunden wird.<br /><br /> Bei nicht reservierten Zeichen mit Escapezeichen werden letztere entfernt.|  
|Vorschlag|Aktualisieren Sie die Anwendungen, um nicht auf „UnescapeDataString“ angewiesen zu sein, um bei einer ungültigen Escapesequenz eine Ausnahme auszulösen. Derartige Sequenzen müssen jetzt direkt erkannt werden.<br /><br /> Erwarten Sie zudem, dass URI- und Datenzeichenfolgen mit und ohne Escapezeichen zwischen .NET 4.0 und .NET 4.5 möglicherweise abweichen und für .NET-Versionen nicht direkt verglichen werden sollten. Stattdessen sollten sie in einer einzelnen .NET-Version analysiert und normalisiert werden, bevor Vergleiche durchgeführt werden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|Analyzer|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: System.NET.PeerToPeer.Collaboration ist unter Windows 8 nicht verfügbar.  
  
|||  
|-|-|  
|Details|Der System.Net.PeerToPeer.Collaboration-Namespace ist unter Windows 8 oder höher nicht verfügbar.|  
|Vorschlag|Apps, die Windows 8 oder höher unterstützen, müssen aktualisiert werden, damit sie von diesem Namespace oder seinen Membern nicht abhängig sind.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|Analyzer|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: MEF-Kataloge implementieren „IEnumerable“ und können daher nicht mehr verwendet werden, um ein Serialisierungsprogramm zu erstellen.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5 implementieren MEF-Kataloge „IEnumerable“ und können daher nicht mehr verwendet werden, um ein Serialisierungsprogramm (XmlSerializer-Objekt) zu erstellen. Wenn Sie versuchen, einen MEF-Katalog zu serialisieren, wird eine Ausnahme ausgelöst.|  
|Vorschlag|MEF kann nicht mehr zum Erstellen eines Serialisierungsprogramms verwendet werden.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: Fehlender Zielframeworkmoniker führt zum Verhalten der Version 4.0.  
  
|||  
|-|-|  
|Details|Anwendungen, bei denen auf Assemblyebene kein [TargetFrameworkAttribute](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) angewendet wurde, werden automatisch mit der Semantik (Quirks) von .NET Framework 4.0 ausgeführt. Um eine hohe Qualität sicherzustellen, empfiehlt es sich, dass alle Binärdateien ein „TargetFrameworkAttribute“ als Attribut erhalten, wodurch die Version von .NET Framework angegeben wird, mit denen sie erstellt wurden. Beachten Sie, dass die Verwendung eines Zielframeworkmonikers in einer Projektdatei dazu führt, dass MSBuild automatisch ein „TargetFrameworkAttribute“ anwendet.|  
|Vorschlag|Es sollte ein [Zielframeworkattribut](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) bereitgestellt werden, entweder durch direktes Hinzufügen des Attributs zur Assembly oder durch Angeben eines Zielframeworks in der [Projektdatei oder über die Visual Studio-GUI für Projekteigenschaften](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: EnableViewStateMac kann nicht länger auf „false“ festgelegt werden.  
  
|||  
|-|-|  
|Details|In ASP.NET sind die folgenden Angaben nicht mehr erlaubt: `<pages enableViewStateMac="false"/>` oder `<@Page EnableViewStateMac="false" %>`. Der Nachrichtenauthentifizierungscode (MAC) des Ansichtszustands wird nun für alle Anfragen mit eingebettetem Ansichtszustand erzwungen. Es sind nur Apps betroffen, die die EnableViewStateMac-Eigenschaft explizit auf „false“ festlegen.|  
|Vorschlag|Für „EnableViewStateMac“ muss „true“ angenommen werden. Zudem müssen alle sich ergebenden MAC-Fehler aufgelöst werden (wie in [dieser](https://support.microsoft.com/kb/2915218) Anleitung erläutert, die in Abhängigkeit von den Besonderheiten, die zu den MAC-Fehlern führen, mehrere Lösungen enthält).|  
|Bereich|Hauptversion|  
|Version|4.5.2|  
|Typ|Laufzeit|  
|Analyzer|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection\<T>.TryTakeFromAny löst keine Ausnahmen mehr aus.  
  
|||  
|-|-|  
|Details|Wenn eine der Eingabeauflistungen als abgeschlossen markiert ist, gibt `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` nicht länger „-1“ zurück und `BlockingCollection<T>.TakeFromAny` löst keine Ausnahme mehr aus. Diese Änderung ermöglicht das Verwenden von Auflistungen, wenn eine der Auflistungen entweder leer oder abgeschlossen ist, die andere Auflistung aber weiterhin abrufbare Elemente enthält.|  
|Vorschlag|Wenn die Rückgabe von „-1“ durch „TryTakeFromAny“ oder das Auslösen einer Ausnahme durch „TakeFromAny“ für solche Situationen zu Ablaufsteuerungszwecken verwendet wurde, in denen eine blockierende Auflistung abgeschlossen wurde, sollte dieser Code jetzt geändert werden, um `.Any(b => b.IsCompleted)` zum Erkennen dieser Bedingung zu verwenden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analyzer|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException legt Zeilenpositionen jetzt ordnungsgemäß fest.  
  
|||  
|-|-|  
|Details|Wenn der LoadOptions.SetLineInfo-Wert an die Load-Methode übergeben wird und ein Validierungsfehler auftritt, enthalten die Eigenschaften „XmlSchemaException.LineNumber“ und „XmlSchemaException.LinePosition“ jetzt Zeileninformationen.|  
|Vorschlag|Ausnahmebehandlungscode, der davon ausgeht, dass „XmlSchemaException.LineNumber“ und „XmlSchemaException.LinePosition“ nicht festgelegt werden, sollte aktualisiert werden, da diese Eigenschaften jetzt ordnungsgemäß festgelegt werden, wenn „SetLineInfo“ beim Laden von XML verwendet wird.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|Analyzer|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities ist jetzt APTCA.  
  
|||  
|-|-|  
|Details|Die Assembly ist mit dem AllowPartiallyTrustedCallersAttribute-Attribut gekennzeichnet.|  
|Vorschlag|Abgeleitete Klassen können nicht mit „SecurityCriticalAttribute“ gekennzeichnet werden. Zuvor mussten abgeleitete Klassen mit „SecurityCriticalAttribute“ gekennzeichnet werden. Diese Änderung sollte jedoch keine tatsächlichen Auswirkungen haben.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: WorkFlow 3.0-Typen sind veraltet.  
  
|||  
|-|-|  
|Details|WWF 3.0-APIs (Windows Workflow Foundation ) (aus dem System.Workflow-Namespace) sind jetzt veraltet.|  
|Vorschlag|Stattdessen sollten die neuen WWF 4.0-APIs (in System.Activities) verwendet werden. Ein Beispiel zur Verwendung der neuen APIs finden Sie [hier](https://msdn.microsoft.com/library/jj205427.aspx) und weitere Anleitungen sind [hier](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx) verfügbar. Da die WWF-3.0-APIs weiterhin unterstützt werden, können sie verwendet und die Warnung zur Buildzeit vermieden werden, indem sie entweder unterdrückt oder ein älterer Compiler verwendet wird.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Analyzer|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: Einige Drag & Drop-APIs für WorkFlow sind veraltet.  
  
|||  
|-|-|  
|Details|Diese Drag/Drop-API für WorkFlow ist veraltet und führt zu Compilerwarnungen, wenn die App mit Version 4.5 neu erstellt wird.|  
|Vorschlag|Stattdessen sollten neue [DragDropHelper](https://msdn.microsoft.com/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx)-APIs verwendet werden, die Vorgänge mit mehreren Objekten unterstützen. Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden. Die APIs werden weiterhin unterstützt.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|Analyzer|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: Neue (mehrdeutige) Dispatcher.Invoke-Überladungen können zu unterschiedlichem Verhalten führen.  
  
|||  
|-|-|  
|Details|.NET Framework 4.5 fügt neue Überladungen zu „Dispatcher.Invoke“ hinzu, die einen Parameter vom Typ „System.Action“ enthalten. Wenn vorhandener Code erneut kompiliert wird, lösen die Compiler möglicherweise Aufrufe der Dispatcher.Invoke-Methoden, die einen Delegate-Parameter aufweisen, als Aufrufe von Dispatcher.Invoke-Methoden mit einem System.Action-Parameter auf. Wird ein Aufruf an eine Dispatcher.Invoke-Überladung mit einem Delegate-Parameter als Aufruf an eine Dispatcher.Invoke-Überladung mit einem System.Action-Parameter aufgelöst, kann es zu folgenden unterschiedlichen Verhaltensweisen kommen:<br /><br /> Wenn eine Ausnahme auftritt, werden die Ereignisse „Dispatcher.UnhandledExceptionFilter“ und „Dispatcher.UnhandledException“ nicht ausgelöst. Stattdessen werden Ausnahmen vom UnobservedTaskException-Ereignis behandelt.<br /><br /> Bis der Vorgang abgeschlossen ist, werden Aufrufe an einige Member, z. B. DispatcherOperation.Result, blockiert.|  
|Vorschlag|Um Unklarheiten zu vermeiden (und mögliche Abweichungen bei der Ausnahmebehandlung oder bei blockierendem Verhalten), kann Code, der „Dispatcher.Invoke“ aufruft, ein leeres Objekt [] als zweiten Parameter an den Invoke-Aufruf übergeben, um sicherzustellen, dass nach der .NET 4.0-Methodenüberladung aufgelöst wird.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|Analyzer|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: EncoderParameter ctor ist veraltet.  
  
|||  
|-|-|  
|Details|Der `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)`-Konstruktor ist jetzt veraltet und gibt Buildwarnungen aus, wenn er verwendet wird.|  
|Vorschlag|Obwohl der `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)`-Konstruktor weiterhin funktioniert, sollte stattdessen der folgende Konstruktor verwendet werden, um die veraltete Buildwarnung zu vermeiden, wenn Code mit .NET 4.5-Tools erneut kompiliert wird: [EncoderParameter.EncoderParameter(Encoder, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/library/hh875096\(v=vs.110\).aspx).|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analyzer|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: Änderung des Verhaltens für Task.WaitAll-Methoden mit Timeout-Argumenten.  
  
|||  
|-|-|  
|Details|Das Task.WaitAll-Verhalten wurde in .NET 4.5 konsistenter gestaltet.<br /><br /> In .NET Framework 4 war das Verhalten dieser Methoden inkonsistent. Wenn vor dem abgelaufenen Timeoutintervall eine oder mehrere Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, löste die Methode eine AggregateException-Ausnahme aus. Wenn vor dem abgelaufenen Timeoutintervall keine Aufgaben vor dem Methodenaufruf abgeschlossen oder abgebrochen wurden, aber eine oder mehrere Aufgaben nach dem Methodenaufruf in diesen Zustand eingetreten waren, gab die Methode „false“ zurück.<br />In .NET Framework 4.5 geben diese Methodenüberladungen jetzt „false“ zurück, falls noch Aufgaben ausgeführt werden, wenn das Timeoutintervall abläuft, und sie lösen nur dann eine AggregateException-Ausnahme aus, wenn eine Eingabeaufgabe abgebrochen wurde (unabhängig davon, ob dies vor oder nach dem Aufruf der Methode erfolgt ist) und keine anderen Aufgaben mehr ausgeführt werden.|  
|Vorschlag|Wenn eine AggregateException als Mittel zum Erkennen einer Aufgabe abgefangen wurde, die vor dem WaitAll-Aufruf abgebrochen wurde, sollte dieser Code stattdessen dieselbe Erkennung über die IsCanceled-Eigenschaft durchführen (Beispiel: .Any(t => t.IsCanceled)), da .NET 4.6 nur in dem Fall eine Ausnahme auslöst, wenn alle erwarteten Aufgaben vor dem Timeout abgeschlossen sind.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Analyzer|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: Änderung des Verhaltens in DDL-APIs (Data Definition Language, Datendefinitionssprachen)  
  
|||  
|-|-|  
|Details|Das Verhalten von DDL-APIs beim Angeben von „AttachDBFilename“ hat sich wie folgt geändert:<br /><br /> Verbindungszeichenfolgen müssen keinen „Initial Catalog“-Wert angeben. Zuvor waren „AttatchDBFilename“ und „Initial Catalog“ erforderlich.<br /><br /> Wenn „AttatchDBFilename“ und „Initial Catalog“ angegeben sind und die angegebene MDF-Datei vorhanden ist, gibt die ObjectContext.DatabaseExists-Methode den Wert „true“ zurück. Bislang hat sie „false“ zurückgegeben.<br /><br /> Wenn „AttatchDBFilename“ und „Initial Catalog“ angegeben sind und die angegebene MDF-Datei vorhanden ist, löscht der Aufruf der ObjectContext.DeleteDatabase-Methode die Dateien.<br /><br /> Wenn „ObjectContext.DeleteDatabase“ aufgerufen wird, wenn die Verbindungszeichenfolge einen AttachDBFilename-Wert mit einer nicht vorhandenen MDF-Datei und einem nicht vorhandenen „Initial Catalog“ angibt, löst die Methode eine InvalidOperationException-Ausnahme aus. Zuvor hat sie eine SqlException-Ausnahme ausgelöst.|  
|Vorschlag|Diese Änderungen erleichtern das Erstellen von Tools und Anwendungen, die die DDL-APIs verwenden. Diese Änderungen können sich in den folgenden Szenarien auf die Anwendungskompatibilität auswirken:<br /><br /> Der Benutzer schreibt Code, der einen DROP DATABASE-Befehl direkt ausführt, anstatt „ObjectContext.DeleteDatabase“ aufzurufen, wenn „ObjectContext.DatabaseExists“ den Wert „true“ zurückgibt. Ist die Datenbank nicht angefügt, die MDF-Datei jedoch vorhanden, wird vorhandener Code hierdurch unbrauchbar.<br /><br /> Der Benutzer schreibt Code, der erwartet, dass die ObjectContext.DeleteDatabase-Methode anstelle einer InvalidOperationException-Ausnahme eine SqlException-Ausnahme auslöst, wenn „Initial Catalog“ und die MDF-Datei nicht vorhanden sind.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: Die Methoden MachineKey.Encode und MachineKey.Decode sind jetzt veraltet.  
  
|||  
|-|-|  
|Details|Diese Methoden sind jetzt veraltet. Die Kompilierung von Code, der diese Methoden aufruft, erzeugt eine Compilerwarnung.|  
|Vorschlag|Die empfohlenen Alternativen sind [MachineKey.Protect](https://msdn.microsoft.com/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) und [MachineKey.Unprotect](https://msdn.microsoft.com/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx). Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden. Die APIs werden weiterhin unterstützt.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> <xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|Analyzer|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: Die Replace-Methode in OData-URLs ist standardmäßig deaktiviert.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5 ist die Replace-Methode in OData-URLs standardmäßig deaktiviert. Wenn „Replace“ für OData (jetzt standardmäßig) deaktiviert ist, schlagen alle Benutzeranforderungen fehl, einschließlich der Ersetzungsfunktionen (die nicht üblich sind).|  
|Vorschlag|Wenn die Replace-Methode erforderlich ist (was nicht üblich ist), kann sie über ein [config settings](https://msdn.microsoft.com/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx) erneut aktiviert werden. Eine aktivierte Replace-Methode kann jedoch Sicherheitslücken öffnen und sollte nur nach sorgfältiger Prüfung verwendet werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|Analyzer|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: Das System.ServiceModel.Web.WebServiceHost-Objekt fügt keinen standardmäßigen Endpunkt mehr hinzu.  
  
|||  
|-|-|  
|Details|Das System.ServiceModel.Web.WebServiceHost-Objekt fügt keinen standardmäßigen Endpunkt mehr hinzu, wenn ein expliziter Endpunkt vom Anwendungscode hinzugefügt wurde.|  
|Vorschlag|Wenn Benutzer erwarten, dass sie eine Verbindung mit einem standardmäßigen Endpunkt herstellen können und andere explizite Endpunkte zu „WebServiceHost“ hinzugefügt wurden, sollten die standardmäßigen Endpunkte auch explizit hinzugefügt werden (mit „AddDefaultEndpoints“).|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|Analyzer|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: „EventSource.WriteEvent impls“ muss denselben Parameter an WriteEvent übergeben, den es erhalten hat (plus ID).  
  
|||  
|-|-|  
|Details|Die Laufzeit erzwingt jetzt den Vertrag, der Folgendes angibt: Eine Klasse, die von EventSource abgeleitet wird und eine ETW-Ereignismethode definiert, muss die EventSource.WriteEvent-Methode der Basisklasse mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die an die ETW-Ereignismethode übergeben wurden, aufrufen.|  
|Vorschlag|Eine IndexOutOfRangeException-Ausnahme wird ausgelöst, wenn ein EventListener entsprechende EventSource-Daten im Prozess für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Analyzer|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: MinFreeMemoryPercentageToActiveService wird jetzt eingehalten.  
  
|||  
|-|-|  
|Details|Diese Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann. Sie ist dafür vorgesehen, OutOfMemoryException-Ausnahmen zu verhindern. In .NET Framework 4.5 hatte diese Einstellung keine Auswirkung. In .NET Framework 4.5.1 wird die Einstellung beobachtet.|  
|Vorschlag|Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist. Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Analyzer|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: Die DTD-Entitätserweiterung „XmlTextReader“ ist auf 10.000.000 Zeichen beschränkt.  
  
|||  
|-|-|  
|Details|Die DTD-Entitätserweiterung ist jetzt auf 10.000.000 Zeichen beschränkt. Das Laden von XML-Dateien ohne DTD-Entitätserweiterung oder mit eingeschränkter DTD-Entitätserweiterung ist davon nicht betroffen. Dateien mit DTD-Entitäten, die auf mehr als 10.000.000 Zeichen erweitert werden, können nicht geladen werden und lösen nun eine Ausnahme aus.|  
|Vorschlag|Wenn das Limit der DTD-Entitätserweiterung von 10.000.000 zu niedrig ist, kann der Wert mit der [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx)-Eigenschaft außer Kraft gesetzt werden. Ein „XmlReaderSettings“ mit dem richtigen MaxCharactersFromEntity-Wert kann an [XmlReader.Create](https://msdn.microsoft.com/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx) übergeben werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|Analyzer|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: Ausnahmemeldung für XSLT-Stylesheet wurde geändert.  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 lautet die Fehlermeldung bei einer zu komplexen XSLT-Datei wie folgt: „Das Stylesheet ist zu komplex.“ In früheren Versionen hieß die Fehlermeldung "XSLT-Compilerfehler." Anwendungscode, der vom Text der Fehlermeldung abhängt, funktioniert nicht mehr. Die Ausnahmetypen sind jedoch nach wie vor identisch, daher sollte diese Änderung keine tatsächlichen Auswirkungen haben.|  
|Vorschlag|Aktualisieren Sie jeglichen App-Code so, dass er von der Ausnahmemeldung dieser Fehlerbedingung abhängig ist, um die neue Meldung zu erwarten, oder (noch besser) aktualisieren Sie den Code so, dass er nur vom Ausnahmetyp abhängig ([XsltException](https://msdn.microsoft.com/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx)) ist, der nicht geändert wurde.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|Analyzer|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF serialisiert Expressions.Literal\<T> DateTimes jetzt anders (unterbricht benutzerdefinierte XAML-Parser).  
  
|||  
|-|-|  
|Details|Das zugeordnete [ValueSerializer](https://msdn.microsoft.com/library/system.windows.markup.valueserializer\(v=vs.110\).aspx)-Objekt konvertiert ein DateTime- oder DateTimeOffset-Objekt, dessen Komponenten für Sekunden und Millisekunden ungleich NULL sind und (für einen DateTime-Wert) dessen DateTime.Kind-Eigenschaft nicht „Unspecified“ ist, in eine Eigenschaftenelementsyntax anstatt in eine Zeichenfolge. Diese Änderung ermöglicht einen Roundtrip für „DateTime“- und „DateTimeOffset“-Werte. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|  
|Vorschlag|Diese Änderung ermöglicht einen Roundtrip für „DateTime“- und „DateTimeOffset“-Werte. Benutzerdefinierte XAML-Parser, die davon ausgehen, dass sich Eingabe-XAML in der Attributsyntax befindet, funktionieren nicht ordnungsgemäß.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: Neue Enumerationswerte in PageRangeSelection von WPF.  
  
|||  
|-|-|  
|Details|Es wurden zwei neue Elemente (CurrentPage und SelectedPage) zur [PageRangeSelection](https://msdn.microsoft.com/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx)-Enumeration hinzugefügt.|  
|Vorschlag|In den meisten Fällen wirken sich diese Änderungen nicht auf Benutzercode aus. Code, der von einer bestimmten Anzahl von Elementen abhängig ist, die in Enum.GetNames- oder Enum.GetValues-Aufrufen für den PageRangeSelection-Typ vorhanden sind, sollte jedoch geändert werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|Analyzer|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: WPF DispatcherSynchronizationContext.CreateCopy gibt jetzt anstelle der aktuellen Instanz eine neue Kopie zurück.  
  
|||  
|-|-|  
|Details|In .NET Framework 4 hat „DispatcherSynchronizationContext.CreateCopy()“ in erster Linie einen Verweis auf die aktuelle Instanz zurückgegeben, um die Leistung zu optimieren. In .NET Framework 4.5 wird eine neue Instanz zurückgegeben, wodurch es erstmalig möglich ist zu Schlussfolgern, dass gleiche Verweise angeben, dass sich der ausführende Thread im richtigen Synchronisierungskontext befindet.  Es ist unwahrscheinlich, dass Code, der die Identität dieser Verweise prüft, betroffen ist. Aber aufgrund der Änderung sollte Code, der „DispatcherSynchronizationContext.CreateCopy“ aufruft, im Rahmen der Migration zu .NET Framework 4.5 oder einer höheren Version getestet werden.|  
|Vorschlag|Beachten Sie, dass „DispatcherSynchronizationContext.CreateCopy()“ jetzt ein neues SynchronizationContext-Objekt zurückgibt.  Zuvor wurde Code, der die Gleichheit von Verweisen verwendete, die auf diese Weise generiert wurden, tatsächlich nicht dahingehend überprüft, ob er sich im richtigen Kontext befunden hat. Dies wird jetzt jedoch durchgeführt, wenn bei der Erstellung .NET 4.5 oder höher verwendet wird.  Obwohl es unwahrscheinlich ist, dass dies zu Problemen führt, sollte das Anwenden der betroffenen Codepfade ausreichend sein, um zu ermitteln, ob dies zu Problemen führen kann.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|Analyzer|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: System.Threading.Tasks.Task löst kein ObjectDisposedException mehr aus, nachdem das Objekt verworfen wurde.  
  
|||  
|-|-|  
|Details|Mit Ausnahme von „Task.IAsyncResult.AsyncWaitHandle“ lösen System.Threading.Tasks.Task-Methoden keine ObjectDisposedException-Ausnahme mehr aus, nachdem das Objekt verworfen wurde.<br />Diese Änderung unterstützt die Verwendung von zwischengespeicherten Aufgaben. Beispielsweise kann eine Methode eine zwischengespeicherte Aufgabe zurückgeben, um einen bereits abgeschlossenen Vorgang darzustellen, anstatt eine neue Aufgabe zuzuordnen. Dies war in früheren .NET Framework-Versionen nicht möglich, da jeder Consumer der Aufgabe diese freigeben konnte und somit unbrauchbar machte.|  
|Vorschlag|Denken Sie daran, dass Task-Methoden in Situationen, in denen das Objekt verworfen wird, keine ObjectDisposedExceptions mehr auslösen. Wenn eine App von dieser Ausnahme (zu wissen, dass ein Task verworfen wurde) abhängig war, sollte sie explizit aktualisiert werden, um den Taskstatus mithilfe von [Task.Status](https://msdn.microsoft.com/library/system.threading.tasks.task.status\(v=vs.110\).aspx) zu prüfen.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: Unterschiedliche Ausnahmebehandlung für die Methoden ObjectContext.CreateDatabase und DbProviderServices.CreateDatabase.  
  
|||  
|-|-|  
|Details|Ab .NET 4.5 versuchen `CreateDatabase`-Methoden eine leere Datenbank zu löschen, wenn die Datenbankerstellung fehlgeschlagen ist. Wenn dieser Vorgang erfolgreich ist, wird die ursprüngliche `SQLException` verbreitet (anstelle der `InvalidOperationException`, die in .NET 4.0 immer ausgelöst wurde).|  
|Vorschlag|Wenn ein „InvalidOperationException“ während der Ausführung von „ObjectContext.CreateDatabase“ oder „DbProviderServices.CreateDatabase“ abgefangen wird, sollten jetzt auch „SQLExceptions“ abgefangen werden.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analyzer|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: ObjectContext.Translate und ObjectContext.ExecuteStoreQuery unterstützen jetzt den Enumerationstyp.  
  
|||  
|-|-|  
|Details|In .NET 4.0 konnte der generische Parameter `T` von `ObjectContext.Translate`- und `ObjectContext.ExecuteStoreQuery`-Methoden kein Enumerationstyp sein. Dieses Szenario wird jetzt unterstützt.|  
|Vorschlag|Wenn für einen Enumerationstyp in .NET 4.0 „Translate“ oder „ExecuteStoreQuery“ aufgerufen wurde, wurde „0“ zurückgegeben. Wenn dieses Verhalten erwünscht war, sollten die Aufrufe durch eine konstante 0 (oder das entsprechende Enum-Äquivalent) ersetzt werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|Analyzer|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty\<TResult> gibt immer die zwischengespeicherte Instanz zurück.  
  
|||  
|-|-|  
|Details|Ab .NET 4.5 gibt `Enumerable.Empty` immer eine zwischengespeicherte interne Instanz `IEnumerable<T>` zurück.<br /><br /> Zuvor hätte `Enumerable.Empty` beim Aufruf der API eine leere `IEnumerable<T>` zwischengespeichert und somit unter bestimmten Umständen, bei denen `Enumerable.Empty` schnell und gleichzeitig aufgerufen wurde, verschiedene Instanzen des Typs für unterschiedliche Aufrufe der API zurückgegeben.|  
|Vorschlag|Da das vorherige Verhalten nicht deterministisch war, ist es unwahrscheinlich, dass der Code davon abhängig ist. Jedoch für den unwahrscheinlichen Fall, dass leere Enumerables verglichen werden und dabei erwartet wird, dass diese gelegentlich ungleich sind, sollten explizite leere Arrays erstellt werden (`new T[0]`), anstatt `Enumerable.Empty` zu verwenden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|Analyzer|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: HttpRequest.ContentEncoding-Eigenschaft verhindert UTF7.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5 ist die UTF-7-Codierung in HttpRequests-Texten nicht zulässig. Teilweise treten bei Daten für Anwendungen, die von eingehenden UTF-7-Daten abhängen, Decodierungsprobleme auf.|  
|Vorschlag|Im Idealfall sollten Anwendungen aktualisiert verwenden, damit sie die UTF-7-Codierung in „HttpRequests“ nicht verwenden. Alternativ kann das Legacyverhalten mithilfe des `aspnet:AllowUtf7RequestContentEncoding`-Attributs des [appSettings](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx)-Elements wiederhergestellt werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|Analyzer|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode versieht kaufmännisches Und-Zeichen mit Escapezeichen.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5 versieht JavaScriptStringEncode das kaufmännische Und-Zeichen (&) mit Escapezeichen.|  
|Vorschlag|Wenn Ihre App vom vorherigen Verhalten dieser Methode abhängig ist, können Sie dem [appSettings-Element von ASP.NET](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx) eine „aspnet:JavaScriptDoNotEncodeAmpersand“-Einstellung in der Konfigurationsdatei hinzufügen.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab.  
  
|||  
|-|-|  
|Details|EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab. NULL-Zeichen werden von der EventSource-Klasse nicht unterstützt. Die Änderung betrifft nur Apps, die EventListener verwenden, um EventSource-Daten im Prozess zu lesen, und die NULL-Zeichen als Trennzeichen verwenden.|  
|Vorschlag|EventSource-Daten sollten nach Möglichkeit aktualisiert werden, damit sie keine eingebetteten NULL-Zeichen verwenden.|  
|Bereich|Kante|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName>|  
|Analyzer|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: ObsoleteAttribute wird in WinMD-Szenarien sowohl als ObsoleteAttribute als auch als DeprecatedAttribute exportiert.  
  
|||  
|-|-|  
|Details|Wenn Sie eine Windows-Metadatenbibliothek (WINMD-Datei) erstellen, wird das ObsoleteAttribute-Attribut als „ObsoleteAttribute“ und als „Windows.Foundation.DeprecatedAttribute“ exportiert.|  
|Vorschlag|Die Neukompilierung des vorhandenen Quellcodes, der das ObsoleteAttribute-Attribut verwendet, generiert möglicherweise Warnungen beim Verarbeiten des Codes in C++/CX oder JavaScript.<br /><br /> Es empfiehlt sich nicht, sowohl das ObsoleteAttribute-Attribut als auch das „Windows.Foundation.DeprecatedAttribute“ auf Code in verwalteten Assemblys anzuwenden, da dies zu Buildwarnungen führen kann.|  
|Bereich|Kante|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Analyzer|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: Die ResolveAssemblyReference-Aufgabe warnt jetzt bei Abhängigkeiten von der falschen Architektur.  
  
|||  
|-|-|  
|Details|Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht. Dies tritt z. B. auf, wenn eine App, die mit der anycpu-Option kompiliert wurde, einen x86-Verweis enthält. Ein solches Szenario kann einen App-Fehler zur Laufzeit ergeben (in diesem Fall, wenn die App als x64-Prozess bereitgestellt wird).|  
|Vorschlag|Es gibt zwei Bereiche mit Auswirkungen:<br /><br /> Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde. Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.<br /><br /> Wenn Warnungen wie Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Analyzer|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: WPF TextBox verwendet standardmäßig 100 als Grenzwert für „Rückgängig“.  
  
|||  
|-|-|  
|Details|In .NET 4.5 beträgt der Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zu .NET 4.0, wo der Wert unbegrenzt ist).|  
|Vorschlag|Wenn der Grenzwert von 100 für „Rückgängig“ zu niedrig ist, kann er explizit mit der UndoLimit-Eigenschaft des Textfelds festgelegt werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Analyzer|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: Ausnahmen während der nicht überwachten Verarbeitung in System.Threading.Tasks.Task werden nicht mehr an den Finalizer-Thread weitergegeben.  
  
|||  
|-|-|  
|Details|Da die System.Threading.Tasks.Task-Klasse einen asynchronen Vorgang darstellt, fängt sie alle nicht schwerwiegenden Ausnahmen ab, die während einer asynchronen Verarbeitung auftreten. Wenn eine Ausnahme in .NET Framework 4.5 nicht überwacht wird und der Code nie auf die Aufgabe wartet, wird die Ausnahme nicht mehr im Finalizer-Thread weitergegeben und führt dazu, dass der Prozess während der Garbage Collection abstürzt. Diese Änderung erhöht die Zuverlässigkeit von Anwendungen, die mithilfe der Task-Klasse nicht überwachte asynchrone Verarbeitungen ausführen.|  
|Vorschlag|Wenn eine App von nicht überwachten asynchronen Ausnahmen abhängt, die an den Finalizer-Thread verteilen, kann das vorherige Verhalten wiederhergestellt werden, indem ein entsprechender Handler für das [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx)-Ereignis bereitgestellt oder ein [Runtimekonfigurationselement](https://msdn.microsoft.com/library/jj160346%28v=vs.110%29.aspx) festgelegt wird.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|Analyzer|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: Die IAsyncResult.CompletedSynchronously-Eigenschaft muss korrekt sein, damit die resultierende Aufgabe abgeschlossen wird.  
  
|||  
|-|-|  
|Details|Wenn Sie TaskFactory.FromAsync aufrufen, muss die Implementierung der IAsyncResult.CompletedSynchronously-Eigenschaft korrekt sein, damit die resultierende Aufgabe abgeschlossen wird. Das heißt, die Eigenschaft muss für den Fall, und ausschließlich für den Fall, dass die Implementierung synchron abgeschlossen wurde, „true“ zurückgeben. Zuvor wurde die Eigenschaft nicht überprüft.|  
|Vorschlag|Wenn IAsyncResult-Implementierungen nur dann ordnungsgemäß „true“ für die CompletedSynchronusly-Eigenschaft zurückgeben, wenn eine Aufgabe synchron abgeschlossen wurde, dann tritt kein Problem auf. Benutzer sollten IAsyncResult-Implementierung überprüfen, die sie (sofern vorhanden) besitzen, um sicherzustellen, dass sie ordnungsgemäß auswerten, ob eine Aufgabe synchron abgeschlossen wurde.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName>|  
|Analyzer|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: Der von der ObjectContext.CreateDatabase-Methode erstellte Protokolldateiname wurde geändert, um den SQL Server-Spezifikationen zu entsprechen.  
  
|||  
|-|-|  
|Details|Wenn die CreateDatabase-Methode entweder direkt oder durch Code First mit dem SqlClient-Anbieter und einem AttachDBFilename-Wert in der Verbindungszeichenfolge aufgerufen wird, erstellt sie eine Protokolldatei namens „Dateiname_log.ldf“ anstelle von „Dateiname.ldf“ (wobei „Dateiname“ der vom AttachDBFilename-Wert angegebene Name der Datei ist). Diese Änderung verbessert das Debuggen, indem eine Protokolldatei bereitgestellt wird, die nach den SQL Server-Spezifikationen benannt wird.|  
|Vorschlag|Wenn der Name der Protokolldatei für eine App wichtig ist, sollte die App aktualisiert werden, um das standardmäßige Dateinamenformat „_log.ldf“ zu erwarten.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Analyzer|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: Das Page.LoadComplete-Ereignis führt nicht mehr dazu, dass das System.Web.UI.WebControls.EntityDataSource-Steuerelement die Datenbindung aufruft.  
  
|||  
|-|-|  
|Details|Das `Page.LoadComplete`-Ereignis führt nicht mehr dazu, dass das System.Web.UI.WebControls.EntityDataSource-Steuerelement Datenbindungen für Änderungen an Erstellungs-/Update-/Löschparametern aufruft. Diese Änderung schließt unnötige Roundtrips zur Datenbank sowie ein Zurücksetzen der Werte von Steuerelementen aus und erzeugt Verhaltensweisen, die mit anderen Datensteuerelementen, z. B. „SqlDataSource“ und „ObjectDataSource“ konsistent sind. Diese Änderung erzeugt im unwahrscheinlichen Fall, dass Anwendungen im `Page.LoadComplete`-Ereignis auf Aufrufen der Datenbindung basieren, ein anderes Verhalten.|  
|Vorschlag|Wenn die Datenbindung erforderlich ist, rufen Sie sie manuell in einem Ereignis auf, das im Postback früher auftritt.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode decodiert keine ungültigen Eingabesequenzen mehr.  
  
|||  
|-|-|  
|Details|Decodierungsmethoden decodieren nicht mehr standardmäßig ungültige Eingabesequenzen in ungültige UTF-16-Zeichenfolgen. Stattdessen geben sie die ursprüngliche Eingabe zurück.|  
|Vorschlag|Die Änderung der Decoderausgabe sollte nur von Bedeutung sein, wenn Sie Binärdaten statt der UTF-16-Daten in Zeichenfolgen speichern. Um dieses Verhalten explizit zu steuern, legen Sie das `aspnet:AllowRelaxedUnicodeDecoding`-Attribut des [appSettings](https://msdn.microsoft.com/library/ms228154\(v=vs.110\).aspx)-Elements auf „true“ fest, um Legacyverhalten zu aktivieren, oder auf „false“, um das aktuelle Verhalten zu aktivieren.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|Analyzer|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: Mit ClickOnce veröffentlichte Apps, die ein SHA-256-Codesignaturzertifikat verwenden, verursachen unter Windows 2003 möglicherweise einen Fehler.  
  
|||  
|-|-|  
|Details|Die ausführbare Datei ist mit SHA256 signiert. Früher wurde sie mit SHA1 signiert, unabhängig davon, ob das Codesignaturzertifikat SHA-1 oder SHA-256 war. Dies gilt für:<br /><br /> Alle Anwendungen, die mit Visual Studio 2012 oder höher erstellt wurden.<br /><br /> Anwendungen, die mit Visual Studio 2010 oder früher auf Systemen mit vorhandenem .NET Framework 4.5 erstellt wurden.<br /><br /> Darüber hinaus wird das ClickOnce-Manifest, wenn .NET Framework 4.5 oder höher vorhanden ist, auch mit SHA-256 für SHA-256-Zertifikate signiert, unabhängig von der .NET Framework-Version, mit der es kompiliert wurde.|  
|Vorschlag|Die Änderung bei der Signierung der ausführbaren ClickOnce-Datei betrifft nur Windows Server 2003-Systeme. Für diese ist die Installation von KB 938397 erforderlich.<br /><br /> Die Änderung bei der Signierung des Manifests mit SHA-256, selbst wenn eine App auf .NET Framework 4.0 oder frühere Versionen abzielt, führt eine Laufzeitabhängigkeit von .NET Framework 4.5 oder einer höheren Version ein.|  
|Bereich|Kante|  
|Version|4.5-4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision und DbParameter.Scale sind jetzt öffentliche virtuelle Member.  
  
|||  
|-|-|  
|Details|DbParameter.Precision und DbParameter.Scale sind als öffentliche virtuelle Eigenschaften implementiert. Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen „DbParameter.IDbDataParameter.Precision“ und „DbParameter.IDbDataParameter.Scale“.|  
|Vorschlag|Wenn Sie einen ADO.NET-Datenbankanbieter neu erstellen, erfordern diese Unterschiede die Anwendung des Schlüsselworts „override“ auf die Eigenschaften „Precision“ und „Scale“. Dies ist nur beim erneuten Erstellen von Komponenten erforderlich. Vorhandene Binärdateien funktionieren weiterhin.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|Analyzer|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData ruft Daten jetzt als UTF-8 ab.  
  
|||  
|-|-|  
|Details|Für Apps, die auf .NET Framework 4.0 ausgerichtet sind oder unter .NET Framework 4.5.1 oder älteren Versionen ausgeführt werden, ruft „DataObject.GetData“ entsprechende HTML-formatierte Daten als ASCII-Zeichenfolge ab. Als Resultat werden nicht-ASCII-Zeichen (Zeichen mit ASCII-Codes größer als 0x7F) durch zwei zufällige Zeichen dargestellt.<br /><br /> In Apps, die .NET Framework 4.5 oder eine neuere Version als Ziel verwenden und unter .NET Framework 4.5.2 ausgeführt werden, ruft `DataObject.GetData` HTML-formatierte Daten als UTF-8 ab und stellt Zeichen größer als „0x7F“ korrekt dar.|  
|Vorschlag|Wenn Sie eine Problemumgehung für das Codierungsproblem mit HTML-formatierten Zeichenfolgen implementiert haben (z. B. durch explizites Codieren der HTML-Zeichenfolge aus der Zwischenablage durch Übergabe an die UTF8Encoding.GetString-Methode) und das Ziel Ihrer App von Version 4 zu 4.5 ändern, sollten Sie diese Problemumgehung entfernen.<br /><br /> Wenn aus irgendeinem Grund das alte Verhalten erforderlich ist, kann die App auf .NET Framework 4.0 ausgerichtet werden, um dieses Verhalten zu erreichen.|  
|Bereich|Kante|  
|Version|4.5.2|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|Analyzer|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: TargetFrameworkName für die Standardanwendungsdomäne erhält nicht mehr standardmäßig den Wert NULL, wenn kein Wert festgelegt wurde.  
  
|||  
|-|-|  
|Details|„TargetFrameworkName“ erhielt bereits in der Standardanwendungsdomäne den Wert NULL, sofern kein Wert explizit festgelegt wurde. Ab Version 4.6 weist die TargetFrameworkName-Eigenschaft für die Standardanwendungsdomäne einen Standardwert auf, der von „TargetFrameworkAttribute“ (sofern vorhanden) abgeleitet ist. Nicht standardmäßige Anwendungsdomänen erben ihr „TargetFrameworkName“ weiterhin von der Standardanwendungsdomäne (die in Version 4.6 nicht standardmäßig auf NULL festgelegt ist), sofern sie nicht explizit außer Kraft gesetzt wird.|  
|Vorschlag|Der Code sollte aktualisiert werden, um nicht davon abhängig zu sein, dass `AppDomainSetup.TargetFrameworkName` standardmäßig NULL verwendet. Wenn es erforderlich ist, dass diese Eigenschaft weiterhin zu NULL ausgewertet wird, kann dieser Wert explizit festgelegt werden.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|Analyzer|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: X509Certificate2.ToString(bool) wird jetzt nicht ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann.  
  
|||  
|-|-|  
|Details|Zuvor wurde diese Methode ausgelöst, wenn „true“ für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden. Nun wird die Methode erfolgreich ausgeführt und sie gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.|  
|Vorschlag|Jeder von „X509Certificate2.ToString(bool)“ abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z. B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in den zuvor die API ausgelöst worden wäre.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden.  
  
|||  
|-|-|  
|Details|Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden. Die folgenden Typen sind betroffen:<br /><br /> Assembly<br /><br /> MemberInfo (und seine abgeleiteten Typen, einschließlich FieldInfo, MethodInfo, Type und TypeInfo)<br /><br /> MethodBody<br /><br /> Modul<br /><br /> ParameterInfo.<br /><br /> Aufrufe von `IMarshal` für das Objekt geben `E_NOINTERFACE` zurück.|  
|Vorschlag|Aktualisieren Sie den Marshallingcode, damit dieser mit Nicht-Reflection-Objekten arbeitet.|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Laufzeit|  
|Analyzer|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition DateTimes gibt eine etwas andere Zeichenfolge zurück.  
  
|||  
|-|-|  
|Details|Zeichenfolgendarstellungen von „ContentDispositions“ wurden ab Version 4.6 aktualisiert, um die Stundenkomponente von „DateTime“ immer durch zwei Ziffern darzustellen. Dies dient zur Einhaltung von [RFC822](http://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](http://www.ietf.org/rfc/rfc2822.txt). Dies bewirkt, dass `ContentDisposition.ToString` in Version 4.6 eine etwas andere Zeichenfolge in Szenarien zurückgibt, bei denen eines der Zeitelemente der Anordnung vor 10:00 Uhr liegt. Beachten Sie, dass „ContentDispositions“ manchmal durch Konvertierung in Zeichenfolgen serialisiert wird, daher sollten alle „ContentDisposition ToString“-Vorgänge, Serialisierungen oder GetHashCode-Aufrufe überprüft werden.|  
|Vorschlag|Erwarten Sie nicht, dass die Zeichenfolgendarstellungen von „ContentDispositions“ aus verschiedenen Versionen von .NET Framework ordnungsgemäß miteinander verglichen werden können. Konvertieren Sie die Zeichenfolgen wieder in „ContentDispositions“, sofern möglich, bevor Sie einen Vergleich durchführen.|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|Analyzer|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load entfernt die Symbol-Eigenschaft nicht.  
  
|||  
|-|-|  
|Details|Wenn der Workflow-Designer auf .NET Framework 4.5 ausgerichtet ist und ein neu gehosteter Workflow der Version 3.5 mit der WorkflowDesigner.Load()-Methode geladen wird, wird beim Speichern des Workflows eine „XamlDuplicateMemberException“ ausgelöst.|  
|Vorschlag|Dieser Fehler wird nur offenkundig, wenn der Workflow-Designer auf .NET Framework 4.5 ausgerichtet ist. Daher kann das Problem umgangen werden, indem `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` auf .NET Framework 4.0 festgelegt wird.<br /><br /> Alternativ kann das Problem vermieden werden, indem der Workflow mithilfe der [WorkflowContext.Load(string)](https://msdn.microsoft.com/library/ee425926\(v=vs.110\).aspx)-Methode anstatt mit [WorkflowDesigner.Load()](https://msdn.microsoft.com/library/ee403482\(v=vs.110\).aspx) geladen wird.|  
|Bereich|Hauptversion|  
|Version|4.5-4.5.2|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|Analyzer|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open schlägt unter Windows 7 mit vorhandenem Nicht-IFS-Winsock-BSP oder -LSP fehl.  
  
|||  
|-|-|  
|Details|Bei „SqlConneciton.Open“ und „OpenAsync“ tritt in .NET Framework 4.5 bei der Ausführung auf einem Windows 7-Computer ein Fehler auf, wenn ein Nicht-IFS-Winsock-BSP oder -LSP auf dem Computer vorhanden ist.<br /><br /> Verwenden Sie den `netsh WinSock Show Catalog`-Befehl, und untersuchen Sie jedes zurückgegebene `Winsock Catalog Provider Entry`-Element, um zu ermitteln, ob ein Nicht-IFS-BSP oder -LSP installiert ist. Wenn für den Servicekennzeichenwert das `0x20000`-Bit gesetzt ist, verwendet der Anbieter IFS-Handle und funktioniert daher ordnungsgemäß. Wenn das `0x20000`-Bit leer (nicht festgelegt) ist, handelt es sich um ein Nicht-IFS-BSP oder -LSP.|  
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden. Alternativ kann es durch Entfernen aller installierten Nicht-IFS-Winsock-LSPs vermieden werden.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5.2|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|Analyzer|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84: Das ICommand.CanExecuteChanged-Ereignisverhalten wurde in .NET 4.5 geändert.  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 wurde ein „CanExecuteChangedEvent“ ignoriert, sofern der Absender des Ereignisses nicht dasselbe Objekt wie das Objekt gewesen ist, das das Ereignis ausgelöst hat. Dieses Problem wurde in Wartungsupdates von .NET Framework 4.5 behoben.|  
|Vorschlag|Dieses Problem wurde in Wartungsreleases von .NET Framework 4.5 behoben, daher kann es vermieden werden, indem Sie sicherstellen, dass .NET Framework auf dem neuesten Stand ist. Sie können auch ein Upgrade auf .NET Framework 4.5.1 durchführen. Alternativ kann „ICommand“ verwendender Code geändert werden, um sicherzustellen, dass der Absender beim Auslösen eines CanExecuteChanged-Befehls dasselbe Objekt ist, das auch das Ereignis auslöst hat.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|Analyzer|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: Einige .NET-APIs führen zu erstmaligen (behandelten) EntryPointNotFoundExceptions.  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 hat eine geringe Anzahl von .NET-Methoden damit begonnen, erstmalige EntryPointNotFoundExceptions auszulösen. Diese Ausnahmen wurden in .NET Framework behandelt, konnten aber die Testautomatisierung unterbrechen, die keine erstmaligen Ausnahmen erwartete. Dieselben APIs stören einige ApiVerifier-Szenarien, wenn „HighVersionLie“ aktiviert ist.|  
|Vorschlag|Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ kann die Testautomatisierung aktualisiert werden, damit keine Störung durch erstmalige „EntryPointNotFoundExceptions“ erfolgt.|  
|Bereich|Kante|  
|Version|4.5-4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|Analyzer|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: Das Scrollen bei WPF TreeView oder einem gruppiertem Listenfeld in „VirtualizingStackPanel“ kann zu einer ausbleibenden Reaktion führen.  
  
|||  
|-|-|  
|Details|Das Scrollen für eine WPF-Strukturansicht in .NET Framework 4.5 in einem virtualisierten StackPanel-Element kann zu ausbleibenden Reaktionen führen, wenn im Anzeigebereich Ränder vorhanden sind (z. B. zwischen den Elementen in der Strukturansicht oder für ein ItemsPresenter-Element). Darüber hinaus können in einigen Fällen Elemente unterschiedlicher Größe in der Ansicht zur Instabilität führen, auch wenn keine Ränder vorhanden sind.|  
|Vorschlag|Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden. Alternativ können Ränder aus Ansichtsauflistungen (z. B. TreeViews) in virtualisierten StackPanel-Elementen entfernt werden, wenn alle enthaltenen Elemente dieselbe Größe aufweisen.|  
|Bereich|Hauptversion|  
|Version|4.5-4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.VirtualizingPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom gibt ein falsches Ergebnis für generische Variablen mit Einschränkungen zurück.  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 gibt „Type.IsAssignableFrom“ für alle generischen Typen mit Einschränkungen fälschlicherweise `false` zurück.|  
|Vorschlag|Dieses Problem wurde in einem Wartungsupdate behoben. Aktualisieren Sie .NET Framework 4.5 oder führen Sie ein Upgrade auf .NET Framework 4.5.1 oder höher aus, um dieses Problem zu beheben. Vermeiden Sie alternativ die Verwendung von „IsAssignableFrom“ mit generischen Typen, die bei generischen Parametern Einschränkungen aufweisen. Reflection-APIs können zur Problemumgehung verwendet werden.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|Analyzer|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: EntityFramework 6.0 wird in Apps sehr langsam geladen, die über Visual Studio gestartet wurden.  
  
|||  
|-|-|  
|Details|Das Starten einer App, die EntityFramework 6.0 verwendet, kann über Visual Studio 2013 sehr langsam sein.|  
|Vorschlag|Dieses Problem wurde in EntityFramework 6.0.2 behoben. Aktualisieren Sie EntityFramework, um die Leistungsprobleme zu vermeiden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: Der Abstand für mehrzeilige ASP.NET-Textfelder wurde bei der Verwendung von AntiXSSEncoder geändert.  
  
|||  
|-|-|  
|Details|In .NET Framework 4.0 wurden zwischen Zeilen eines mehrzeiligen Textfelds beim Postback zusätzliche Zeilen eingefügt, wenn `AntiXSSEncoder` verwendet wird. In .NET Framework 4.5 sind diese zusätzlichen Zeilenumbrüche nicht enthalten, wenn die Web-App auf .NET 4.5 ausgerichtet ist.|  
|Vorschlag|Beachten Sie, dass bei Web-Apps der Version 4.0, die auf .NET 4.5 neu ausgerichtet wurden, mehrzeilige Textfelder möglicherweise verbessert wurden, damit diese keine zusätzlichen Zeilenumbrüche mehr einfügen. Wenn dies nicht erwünscht ist, kann die App das alte Verhalten verwenden, wenn sie unter .NET Framework 4.5 ausgeführt wird, indem sie auf .NET Framework 4.0 ausgerichtet wird.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Analyzer|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue\<T>.TryPeek kann über seinen Out-Parameter eine fehlerhafte Null zurückgeben.  
  
|||  
|-|-|  
|Details|In einigen Multithreaded-Szenarien kann `ConcurentQueue<T>.TryPeek` „true“ zurückgeben, aber den Out-Parameter mit einem Nullwert füllen (anstelle des richtigen Werts).|  
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.1 behoben. Dieses Problem wird durch ein Upgrade auf diese .NET Framework-Version behoben.|  
|Bereich|Hauptversion|  
|Version|4.5-4.5.1|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|Analyzer|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: Mehrere Elemente in einer einzelnen TableLayoutPanel-Zelle können neu angeordnet werden.  
  
|||  
|-|-|  
|Details|Wenn in .NET Framework 4.5 mehrere Elemente in derselben TableLayoutPanel-Zelle platziert werden, können sie in einer anderen Reihenfolge als in .NET Framework 4.0 angezeigt werden.|  
|Vorschlag|Dieses Verhalten wurde in einem Wartungsupdate für .NET Framework 4.5 rückgängig gemacht. Aktualisieren Sie .NET Framework 4.5 oder führen Sie ein Upgrade auf .NET Framework 4.5.1 oder höher aus, um dieses Problem zu beheben. Vermeiden Sie alternativ den mehrdeutigen Fall von mehreren Elementen in derselben TableLayourPanel-Zelle.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Analyzer|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: Die Foreach-Iteratorvariable ist jetzt auf die Iteration bezogen, daher unterscheidet sich die Semantik für die Abschlusserfassung (in C# 5)  
  
|||  
|-|-|  
|Details|Ab C# 5 (Visual Studio 2012) sind Foreach-Iteratorvariablen auf die Iteration bezogen. Dies kann zu Unterbrechungen führen, wenn der Code zuvor davon abhängig war, dass die Variablen nicht in den Foreach-Abschluss einbezogen wurden. Diese Änderung führt dazu, dass eine an einen Delegaten übergebene Iteratorvariable als der Wert behandelt wird, den sie zum Zeitpunkt der Erstellung des Delegaten aufwies, anstatt sie als den Wert zu behandeln, den sie zum Zeitpunkt aufwies, als der Delegat aufgerufen wurde.|  
|Vorschlag|Idealerweise sollte der Code aktualisiert werden, um das neue Compilerverhalten zu erwarten. Wenn die alte Semantik erforderlich ist, kann die Iteratorvariable durch eine separate Variable ersetzt werden, die explizit außerhalb des Gültigkeitsbereichs der Schleife platziert wird.|  
|Bereich|Hauptversion|  
|Version|4.5|  
|Typ|Neuzuweisung|  
|Analyzer|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter rendert das Element \`<br/\>` nicht ordnungsgemäß.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.6 fügt der Aufruf von `HtmlTextWriter.RenderBeginTag()` und `HtmlTextWriter.RenderEndTag()` mit einem `<BR />`-Element ordnungsgemäß nur ein (anstatt zwei) `<BR />` ein.|  
|Vorschlag|Wenn eine App vom zusätzlichen `<BR />`-Tag abhängig ist, sollte `HtmlTextWriter.RenderBeginTag()` ein zweites Mal aufgerufen werden. Beachten Sie, das sich dieses Verhalten nur auf Apps auswirkt, die auf .NET Framework 4.6 ausgerichtet sind, daher ist eine weitere Möglichkeit die Ausrichtung auf eine vorherige Version von .NET Framework, um das alte Verhalten zu erhalten.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|Analyzer|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: Das Aufrufen von Items.Refresh für ein WPF-ListBox, -ListView oder -DataGrid mit ausgewählten Einträgen kann dazu führen, dass im Element doppelte Einträge angezeigt werden.  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 kann der Aufruf von „ListBox.Items.Refresh“ mit ausgewählten Einträgen über Code dazu führen, dass die ausgewählten Einträge in der Liste doppelt vorkommen. Ein ähnliches Problem tritt bei „ListView“ und „DataGrid“ auf. Dieses Problem wurde in .NET Framework 4.6 behoben.|  
|Vorschlag|Dieses Problem kann dadurch umgangen werden, dass die Auswahl der Einträge programmgesteuert aufgehoben wird, bevor „Refresh“ aufgerufen wird. Nachdem der Aufruf abgeschlossen ist, werden die Einträge erneut ausgewählt. Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|  
|Bereich|Nebenversion|  
|Version|4.5-4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|Analyzer|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: ETW EventListeners erfassen keine Ereignisse von Anbietern mit expliziten Schlüsselwörtern (wie der TPL-Anbieter).  
  
|||  
|-|-|  
|Details|ETW EventListeners mit leerer Schlüsselwortmaske erfassen Ereignisse von Anbietern mit expliziten Schlüsselwörtern nicht ordnungsgemäß. In .NET Framework 4.5 hat der TPL-Anbieter damit begonnen, explizite Schlüsselwörter bereitzustellen und dadurch dieses Problem ausgelöst. In .NET Framework 4.6 wurde „EventListeners“ aktualisiert, damit dieses Problem nicht mehr auftritt.|  
|Vorschlag|Um dieses Problem zu umgehen, ersetzen Sie Aufrufe von „EnableEvents(eventSource, level)“ durch Aufrufe der EnableEvents-Überladung, die explizit die Maske für beliebige Schlüsselwörter angibt: `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`.<br /><br /> Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.|  
|Bereich|Kante|  
|Version|4.5-4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|Analyzer|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: Beim Erstellen von Entity Framework-EDMX mit Visual Studio 2013 kann der Fehler MSB4062 auftreten, wenn die Aufgaben „EntityDeploySplit“ oder „EntityClean“ verwendet werden.  
  
|||  
|-|-|  
|Details|MSBuild 12.0-Tools (enthalten in Visual Studio 2013) haben die MSBuild-Dateispeicherorte geändert, wodurch ältere Entity Framework-Zieldateien ungültig geworden sind. Das führt dazu, dass `EntityDeploySplit`- und `EntityClean`-Aufgaben fehlschlagen, da sie `Microsoft.Data.Entity.Build.Tasks.dll` nicht finden können. Beachten Sie, dass dieses Problem aufgrund einer Toolsetänderung (msbuild/VS) und nicht aufgrund einer Änderung am .NET Framework auftritt. Es tritt nur beim Upgrade von Entwicklertools und nicht beim Aktualisieren von .NET Framework auf.|  
|Vorschlag|Die Entity Framework-Zieldateien wurden korrigiert, um mit dem neuen MSBuild-Layout zu funktionieren, das ab .NET Framework 4.6 verwendet wird. Ein Upgrade auf diese Version von .NET Framework wird dieses Problem beheben. Alternativ können Sie [diese](http://stackoverflow.com/a/24249247/131944) Problemumgehung verwenden, um die Zieldateien direkt zu patchen.|  
|Bereich|Hauptversion|  
|Version|4.5.1-4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: Die XSD-Schemavalidierung erkennt jetzt Verstöße gegen eindeutige Einschränkungen richtig, wenn Verbundschlüssel verwendet werden und ein Schlüssel leer ist.  
  
|||  
|-|-|  
|Details|Versionen von .NET Framework vor 4.6 wiesen einen Fehler auf, der dazu geführt hat, dass die XSD-Validierung eindeutige Einschränkungen für Verbundschlüssel nicht erkannt hat, wenn einer der Schlüssel leer war. Dieses Problem wurde in .NET Framework 4.6 behoben. Dies führt zu einwandfreieren Validierung, aber möglicherweise auch dazu, dass einige XML-Daten nicht überprüft werden, die zuvor überprüft wurden.|  
|Vorschlag|Wenn eine lockerere Validierung von .NET Framework 4.0 erforderlich ist, kann die überprüfenden Anwendung auf Version 4.5 (oder früher) von .NET Framework ausgerichtet werden. Wenn eine Neuausrichtung auf .NET 4.6 erfolgt, sollte jedoch eine Codeüberprüfung durchgeführt werden, um sicherzustellen, dass die Überprüfung doppelter Verbundschlüssel (wie in dieser Problembeschreibung erläutert) nicht erwartet wird.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: Der Aufruf von Attribute.GetCustomAttributes für eine Indexereigenschaft löst keine AmbiguousMatchException mehr aus, wenn die Mehrdeutigkeit durch den Typ des Indexes aufgelöst werden kann.  
  
|||  
|-|-|  
|Details|Vor .NET Framework 4.6 führte der Aufruf von `GetCustomAttribute(s)` für eine Indexereigenschaft, die sich nur durch den Indextyp von einer anderen Eigenschaft unterschied, zu einer `AmbiguousMatchException`. Ab .NET Framework 4.6 werden die Attribute der Eigenschaft ordnungsgemäß zurückgegeben.|  
|Vorschlag|Beachten Sie, dass „GetCustomAttribute(s)“ jetzt häufiger funktioniert. Wenn sich eine App zuvor auf `AmbiguousMatchException` verlassen hat, sollte jetzt die Reflektion verwendet werden, um stattdessen explizit nach mehreren Indexern zu suchen.|  
|Bereich|Kante|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: Das Scrollen zum untersten Eintrag in ItemsControl-Steuerelementen (z. B. ListBox und DataGrid) war bei Verwendung von benutzerdefinierten DataTemplates zeitweise nicht möglich.  
  
|||  
|-|-|  
|Details|In einigen Fällen verursacht ein Fehler in .NET Framework 4.5, dass ItemsControl-Steuerelemente (z. B. ListBox, ComboBox, DataGrid usw.) nicht zum untersten Eintrag scrollen, wenn benutzerdefinierte DataTemplates verwendet werden. Wenn der Vorgang ein zweites Mal versucht wird (nachdem wieder nach oben gescrollt wurde), funktioniert es entsprechend.|  
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.2 behoben und kann durch ein Upgrade auf diese (oder eine höhere) Version von .NET Framework vermieden werden. Alternativ können Benutzer weiterhin Scrolleisten in diesen Auflistungen ziehen, wobei sie es möglicherweise zweimal versuchen müssen, bis der Vorgang erfolgreich ausgeführt wird.|  
|Bereich|Nebenversion|  
|Version|4.5-4.5.2|  
|Typ|Laufzeit|  
|Analyzer|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: GlyphRun.ComputeInkBoundingBox() und FormattedText.Extent geben seit .NET 4.5 verschiedene Werte zurück.  
  
|||  
|-|-|  
|Details|Es wurden Verbesserungen an „GlyphRun.ComputeInkBoundingBox()“ und „FormattedText.Extent“ in .NET Framework 4.5 vorgenommen, um Probleme zu beheben, bei denen Felder für die darin enthaltenen Glyphen in .NET Framework 4.0 zu klein waren. Aus diesem Grund sind einige Begrenzungsrahmen in .NET Framework 4.5 größer, sodass sich geringfügige Unterschiede beim Layout der Benutzeroberfläche ergeben.|  
|Vorschlag|Beachten Sie, dass einige Begrenzungsrahmen für Glyphen vergrößert wurden. Diese Änderungen verbessert in der Regel die Darstellung und das Testen von Feldtreffern, aber wenn das ältere Verhalten (vor .NET 4.5) gewünscht wird, kann es durch Hinzufügen des folgenden Eintrags zur Datei „app.config“ aktiviert werden:<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|Analyzer|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: Der Aufruf von DataGrid.CommitEdit über einen CellEditEnding-Handler verliert den Fokus.  
  
|||  
|-|-|  
|Details|Der Aufruf von „DataGrid.CommitEdit“ über einen der CellEditEnding-Ereignishandler des Datenrasters führt dazu, dass das Datenraster den Fokus verliert.|  
|Vorschlag|Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden. Alternativ kann es vermieden werden, indem das Datenraster nach dem Aufruf von „CommitEdit“ explizit neu ausgewählt wird.|  
|Bereich|Kante|  
|Version|4.5-4.5.2|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|Analyzer|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC versieht jetzt Leerzeichen in Zeichenfolgen, die über Routenparameter übergeben werden, mit Escapezeichen.  
  
|||  
|-|-|  
|Details|Um RFC 2396 zu entsprechen, werden Leerzeichen in Routenpfaden jetzt beim Auffüllen der Aktionsparameter von einer Route mit Escapezeichen versehen. Während `/controller/action/some data` zuvor mit der Route `/controller/action/{data}` übereinstimmte und `some data` als Datenparameter bereitgestellt wurde, stellt sie daher jetzt `some%20data` bereit.|  
|Vorschlag|Der Code sollte aktualisiert werden, um die Escapezeichen der Zeichenfolgenparameter von einer Route zu entfernen. Wenn der ursprüngliche URI erforderlich ist, kann mithilfe der Request.RequestUri.OriginalString-API darauf zugegriffen werden.|  
|Bereich|Nebenversion|  
|Version|4.5.2|  
|Typ|Laufzeit|  
|Betroffene APIs|[System.Web.Http.RouteAttribute](https://msdn.microsoft.com/library/system.web.http.routeattribute(v=vs.118).aspx)|  
|Analyzer|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET unterstützt die Qualifizierung partieller Namespaces für System.Windows-APIs nicht mehr.  
  
|||  
|-|-|  
|Details|Ab .NET 4.5.2 können VB.NET-Projekte keine System.Windows-APIs mit teilweise qualifizierten Namespaces angeben. Der Verweis auf `Windows.Forms.DialogResult` führt z. B. zu einem Fehler. Stattdessen muss der Code auf den vollqualifizierten Namen (`System.Windows.Forms.DialogResult`) verweisen oder den bestimmten Namespace importieren und dann einfach auf `DialogResult` verweisen.|  
|Vorschlag|Der Code sollte aktualisiert werden, um auf `System.Windows`-APIs mit einfachen Namen (und den entsprechenden Namespace importieren) oder mit vollqualifizierten Namen zu verweisen.|  
|Bereich|Nebenversion|  
|Version|4.5.2|  
|Typ|Neuzuweisung|  
|Analyzer|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: Die bidirektionale Datenbindung an eine Eigenschaft mit einem nicht öffentlichen Setter wird nicht unterstützt.  
  
|||  
|-|-|  
|Details|Der Versuch, Daten ohne einen öffentlichen Setter an eine Eigenschaft zu binden, wurde nie unterstützt. Ab .NET Framework 4.5.1 löst dieses Szenario ein „InvalidOperationException“ aus. Beachten Sie, dass diese neue Ausnahme nur für Apps ausgelöst wird, die speziell auf .NET Framework 4.5.1 abzielen. Wenn eine App auf .NET Framework 4.5 ausgerichtet ist, wird der Aufruf zugelassen. Wenn die App nicht auf eine bestimmte Version von .NET Framework ausgerichtet ist, wird die Bindung als unidirektionale Bindung behandelt.|  
|Vorschlag|Die App sollte aktualisiert werden, um entweder die unidirektionale Bindung zu verwenden oder den Setter der Eigenschaft öffentlich zur Verfügung zu stellen. Alternativ können Sie die App auf .NET Framework 4.5 ausrichten, um das alte Verhalten zu erreichen.|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|Analyzer|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Marshal.SizeOf- und Marshal.PtrToStructure-Überladungen führen bei dynamischem Code zu Unterbrechungen.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5.1 kann das dynamische Binden an die Methoden `Marshal.SizeOf` oder `Marshal.PtrToStructure` (z. B. über Windows PowerShell, IronPython oder das dynamische C#-Schlüsselwort) zu `MethodInvocationExceptions` führen, da neue Überladungen dieser Methoden hinzugefügt wurden, die für die Skriptmodule möglicherweise mehrdeutig sind.|  
|Vorschlag|Aktualisieren Sie die Skripts, um eindeutig anzugeben, welche Überladung verwendet werden muss. Dies kann in der Regel dadurch erreicht werden, dass die Typparameter der Methoden explizit zu `System.Type` umgewandelt werden. Weitere Informationen und Beispiele zur Problemumgehung finden Sie über [diesen Link](https://support.microsoft.com/kb/2909958/).|  
|Bereich|Nebenversion|  
|Version|4.5.1|  
|Typ|Laufzeit|  
|Analyzer|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: PreviewLostKeyboardFocus wird wiederholt aufgerufen, wenn der Handler ein Windows Forms-Meldungsfeld anzeigt.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.5 führt der Aufruf von `System.Windows.Forms.MessageBox.Show` über einen `UIElement.PreviewLostKeyboardFocus`-Handler dazu, dass der Handler erneut auslöst, wenn das Meldungsfeld geschlossen wird, was ggf. zu einer Endlosschleife von Meldungsfeldern führt.|  
|Vorschlag|Es gibt zwei Optionen, um dieses Problem zu umgehen:<br /><br /> Es kann durch Aufrufen von `System.Windows.MessageBox.Show` anstelle von `System.Windows.Forms.MessageBox.Show` vermieden werden.<br /><br /> Es kann durch Anzeigen des Meldungsfelds über einen `LostKeyboardFocus`-Ereignishandler (im Gegensatz zu einem `PreviewLostKeyboardFocus`-Ereignishandler) vermieden werden.|  
|Bereich|Kante|  
|Version|4.5|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|Analyzer|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: Ein in .NET 4.5 mit NetDataContractSerializer serialisiertes ConcurrentDictionary kann nicht von .NET 4.5.1 oder 4.5.2 deserialisiert werden.  
  
|||  
|-|-|  
|Details|Aufgrund der internen Änderungen am Typ können mit `NetDataContractSerializer` in .NET Framework 4.5 serialisierte `System.Collections.Concurrent.ConcurrentDictionary`-Objekte nicht in .NET Framework 4.5.1 oder .NET Framework 4.5.2 deserialisiert werden.<br /><br /> Beachten Sie, dass es in die andere Richtung (mit .NET Framework 4.5.x serialisieren und mit .NET Framework 4.5 deserialisieren) funktioniert. Ebenso funktioniert die versionsübergreifende Serialisierung von 4.x mit .NET Framework 4.6.<br /><br /> Die Serialisierung und Deserialisierung mit einer einzigen Version von .NET Framework ist nicht betroffen.|  
|Vorschlag|Wenn es erforderlich ist, ein „ConcurrentDictionary“ zwischen .NET Framework 4.5 und .NET Framework 4.5.1/4.5.2 zu serialisieren und zu deserialisieren, sollte ein alternatives Serialisierungsprogramm wie „DataContractSerializer“ oder „BinaryFormatter“ anstelle von „NetDataContractSerializer“ verwendet werden.<br /><br /> Da dieses Problem in .NET Framework 4.6 behandelt wurde, kann es möglicherweise durch ein Upgrade auf diese Version von .NET Framework gelöst werden.|  
|Bereich|Nebenversion|  
|Version|4.5.1-4.6|  
|Typ|Laufzeit|  
|Analyzer|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: Der persische Kalender verwendet jetzt den Hijri-Solaralgorithmus.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.6 verwendet die PersianCalendar-Klasse den Hijri-Solaralgorithmus. Das Konvertieren von Datumsangaben zwischen dem persischen und anderen Kalendern erzeugt ab .NET Framework 4.6 für Datumsangaben vor 1800 oder nach 2023 (gregorianisch) möglicherweise ein etwas anderes Ergebnis.<br /><br /> Darüber hinaus ist `PersianCalendar.MinSupportedDateTime` jetzt `March 22, 0622 instead of March 21, 0622`.|  
|Vorschlag|Beachten Sie, dass einige frühe oder späte Datumsangaben bei der Verwendung des persischen Kalenders in .NET 4.6 möglicherweise etwas anders aussehen. Speichern Sie zudem beim Serialisieren von Daten zwischen Prozessen, die möglicherweise unter verschiedenen Versionen von .NET Framework ausgeführt werden, die Daten nicht als PersionCalendar-Datumszeichenfolgen (da diese Werte abweichen können).|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Laufzeit|  
|Betroffene APIs|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|Analyzer|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: Das Aufrufen von CreateDefaultAuthorizationContext mit einem NULL-Argument wurde geändert.  
  
|||  
|-|-|  
|Details|Die Implementierung von „AuthorizationContext“, das von einem Aufruf von `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` mit dem Argument „null authorizationPolicies“ zurückgegeben wurde, hat seine Implementierung in .NET Framework 4.6 geändert.|  
|Vorschlag|In seltenen Fällen liegen bei WCF-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor. In derartigen Fällen gibt es zwei Möglichkeiten, um das vorherige Verhalten wiederherzustellen:<br /><br /> Kompilieren Sie Ihre App erneut, damit sie auf eine frühere Version als .NET Framework 4.6 abzielt. Verwenden Sie für mithilfe von IIS gehosteten Diensten das \<httpRuntime targetFramework="x.x" />-Element, um auf eine frühere Version von .NET Framework abzuzielen.<br /><br /> Fügen Sie dem Abschnitt `<appSettings>` Ihrer Datei „app.config“ die folgende Zeile hinzu: `<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|Analyzer|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: WPF TreeViewItem muss in einem TreeView-Steuerelement verwendet werden.  
  
|||  
|-|-|  
|Details|In .NET Framework 4.5 wurde eine Änderung eingeführt, die die Verwendung von TreeViewItem-Elementen außerhalb eines TreeView-Steuerelements beschränkt. Dieser Fall kann unter den folgenden Bedingungen eintreten:<br /><br /> Das visuelle übergeordnete Element von „TreeViewItem“ ist kein Bereich. (Ein für „TreeView“ generiertes „TreeViewItem“ weist einen Bereich als übergeordnetes Element auf.)<br /><br /> „TreeViewItem“ ist ein Nachfolger von „VirtualizingStackPanel“, das als „Elementhost“ für ein Listensteuerelement (ListBox, DataGrid, ListView usw.) fungiert. Die Virtualisierung muss nicht aktiviert werden.<br /><br /> Einträge können in „VirtualizingStackPanel“ gescrollt werden (`ScrollUnit="Item"`).<br /><br /> Jemand ruft `VirtualizingStackPanel.MakeVisible(v)` auf, um ein Element `v` in eine Ansicht zu scrollen. Dies kann auf verschiedene Arten explizit oder implizit erfolgen. Die am häufigsten verwendeten Methode ist möglicherweise einfach das Klicken auf `v`, damit es den Tastaturfokus erhält.<br /><br /> Die visuelle Kette des übergeordneten Elements von `v` zu „VirtualizingStackPanel“ durchläuft das TreeViewItem-Element.<br /><br /> Das bedeutet, dies wird angezeigt, wenn ein „TreeViewItem“ außerhalb von „TreeView“ verwendet wird und der Benutzer auf einen Nachfolger von „TreeViewItem“ klickt, um ihn anzuzeigen. Wenn „TreeViewItem“ keine Nachfolger besitzt, die den Fokus erhalten können, tritt dieses Problem nicht auf. Ein Beispiel für eine entsprechende Situation liegt vor, wenn „TreeViewItem“ der Stamm von „DataTemplate“ ist.  Wenn dieses Problem erreicht wird, tritt „InvalidCastException“ innerhalb des WPF-Frameworks auf.|  
|Vorschlag|Hierfür wird ein Hotfix zur Verfügung gestellt.|  
|Bereich|Nebenversion|  
|Version|4.5|  
|Typ|Laufzeit|  
|Analyzer|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims berücksichtigt alle Anspruchstypen (claimTypes).  
  
|||  
|-|-|  
|Details|Wenn in Apps, die auf .NET Framework 4.6.1 ausgerichtet sind, ein X509-Anspruchssatz über ein Zertifikat mit mehreren DNS-Einträge im SAN-Feld initialisiert wird, versucht die FindClaims-Methode, das claimType-Argument mit allen DNS-Einträgen abzugleichen.<br /><br /> Bei Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, versucht die FindClaims-Methode, das claimType-Argument nur mit den letzten DNS-Eintrag abzustimmen.|  
|Vorschlag|Diese Änderung wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind. Diese Änderung kann mit dem [DisableMultipleDNSEntries](https://msdn.microsoft.com/library/mt620030%28v=vs.110%29.aspx)-Kompatibilitätsschalter deaktiviert werden (oder aktiviert, bei der Ausrichtung auf Versionen vor 4.6.1).|  
|Bereich|Nebenversion|  
|Version|4.6.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|Analyzer|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage löst für eintrittsinvariante Implementierungen von IMessageFilter.PreFilterMessage nicht mehr aus.  
  
|||  
|-|-|  
|Details|Vor .NET Framework 4.6.1 hat der Aufruf von „Application.FilterMessage“ mit „IMessageFilter.PreFilterMessage“, der „AddMessageFilter“ oder „RemoveMessageFilter“ aufgerufen hat (während auch „Application.DoEvents“ aufgerufen wurde), zu „IndexOutOfRangeException“ geführt.<br /><br /> Seit der Verwendung von Anwendungen, die auf .NET Framework 4.6.1 abzielen, wird diese Ausnahme nicht mehr ausgelöst und es können eintrittsinvariante Filter verwendet werden, wie oben beschrieben.|  
|Vorschlag|Beachten Sie, dass „Application.FilterMessage“ nicht mehr für das oben beschriebene eintrittsinvariante IMessageFilter.PreFilterMessage-Verhalten ausgelöst wird. Dies wirkt sich nur auf Anwendungen aus, die auf .NET Framework 4.6.1 ausgerichtet sind.<br /><br /> Auf .NET Framework 4.6.1 ausgerichtete Apps können diese Änderung mithilfe des [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/library/mt620032%28v=vs.110%29.aspx)-Kompatibilitätsschalters ablehnen (auf ältere Framework-Versionen ausgerichtete Apps können diese Option aktivieren).|  
|Bereich|Kante|  
|Version|4.6.1|  
|Typ|Neuzuweisung|  
|Betroffene APIs|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|Analyzer|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture wird zwischen WPF-Dispatcher-Vorgängen nicht beibehalten.  
  
|||  
|-|-|  
|Details|Ab .NET Framework 4.6 gehen Änderungen an „CurrentCulture“ oder „CurrentUICulture“, die innerhalb eines [Verteilers](https://msdn.microsoft.com/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx) vorgenommen werden, am Ende des Verteilungsvorgangs verloren. Auf ähnliche Weise werden außerhalb des Verteilungsvorgangs vorgenommene Änderungen an „CurrentCulture“ und „CurrentUICulture“ möglicherweise nicht widergespiegelt, wenn der Vorgang ausgeführt wird.<br /><br /> Praktisch gesehen bedeutet dies, dass Änderungen an „CurrentCulture“ und „CurrentUICulture“ zwischen WPF-UI-Rückrufen und anderem Code in einer WPF-Anwendung nicht weitergeben werden.<br /><br /> Der Grund hierfür ist eine Änderung in [ExecutionContext](https://msdn.microsoft.com/library/system.threading.executioncontext%28v=vs.110%29.aspx), die bewirkt, dass „CurrentCulture“ und „CurrentUICulture“ beginnend mit Apps, die auf .NET Framework 4.6 abzielen, im Ausführungskontext gespeichert werden. WPF-Verteilungsvorgänge speichern den Ausführungskontext, der dazu verwendet wurde, um den Vorgang zu beginnen und stellen den vorherigen Kontext wieder her, wenn der Vorgang abgeschlossen ist. Da „CurrentCulture“ und „CurrentUICulture“ jetzt Bestandteil dieses Kontexts sind, bleiben innerhalb eines Verteilungsvorgangs an ihnen vorgenommene Änderungen außerhalb des Vorgangs nicht erhalten.|  
|Vorschlag|Von dieser Änderung betroffene Apps können dieses Problem möglicherweise umgehen, indem das gewünschte „CurrentCulture“ oder „CurrentUICulture“ in einem Feld gespeichert wird und für alle Vorgangstexte der Verteilung geprüft wird (einschließlich der Rückrufereignishandler für Benutzeroberflächenereignisse), ob das richtige „CurrentCulture“ und „CurrentUICulture“ festgelegt ist. Da die ExecutionContext-Änderung, die dieser WPF-Änderung zugrunde liegt, nur Apps betrifft, die auf .NET Framework 4.6 oder höher abzielen, kann diese Unterbrechung alternativ vermieden werden, indem die Ausrichtung auf .NET Framework 4.5.2 erfolgt.|  
|Bereich|Nebenversion|  
|Version|4.6|  
|Typ|Neuzuweisung|  
|Analyzer|CD0145|

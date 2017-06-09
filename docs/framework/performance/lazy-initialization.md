---
title: "Lazy Initialization | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "lazy initialization in .NET, introduction"
ms.assetid: 56b4ae5c-4745-44ff-ad78-ffe4fcde6b9b
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Lazy Initialization
*Verzögerte Initialisierung* eines Objekts bedeutet, dass seine Erstellung verzögert wird, bis es erstmalig verwendet wird. \(Für dieses Thema sind die Begriffe *verzögerte Initialisierung* und *verzögerte Instanziierung* synonym.\) Die verzögerte Initialisierung dient hauptsächlich dazu, die Leistung zu verbessern, unnötige Berechnungen zu vermeiden und die Programmspeicheranforderungen zu reduzieren.  Im Folgenden sind die häufigsten Szenarien aufgeführt:  
  
-   Sie verfügen über ein Objekt, dessen Erstellung teuer ist und das möglicherweise nicht vom Programm verwendet wird.  Angenommen, im Speicher befindet sich ein `Customer`\-Objekt mit einer `Orders`\-Eigenschaft, die ein großes Array von `Order`\-Objekten enthält, für dessen Initialisierung eine Datenbankverbindung erforderlich ist.  Wenn der Benutzer nie anfordert, ein Orders\-Objekt anzuzeigen oder die Daten in einer Berechnung zu verwenden, gibt es keinen Grund, Systemspeicher oder Berechnungszyklen zu verwenden, um es zu erstellen.  Indem Sie `Lazy<Orders>` verwenden, um die verzögerte Initialisierung für das `Orders`\-Objekt zu deklarieren, können Sie vermeiden, dass Systemressourcen verschwendet werden, wenn das Objekt nicht verwendet wird.  
  
-   Sie verfügen über ein Objekt, dessen Erstellung teuer ist und daher verzögert werden soll, bis andere teure Vorgänge abgeschlossen wurden.  Angenommen, das Programm lädt beim Start mehrere Objektinstanzen, aber nur einige davon sind sofort erforderlich.  Sie können die Startleistung des Programms verbessern, indem Sie die Initialisierung der nicht erforderlichen Objekte verzögern, bis die erforderlichen Objekte erstellt wurden.  
  
 Obwohl Sie eigenen Code schreiben können, um die verzögerte Initialisierung auszuführen, empfiehlt es sich, stattdessen <xref:System.Lazy%601> zu verwenden.  <xref:System.Lazy%601> und die dazugehörigen verwandten Typen unterstützen auch Threadsicherheit und stellen eine konsistente Ausnahmeverteilungsrichtlinie bereit.  
  
 In der folgenden Tabelle sind die Typen auflistet, die von .NET Framework Version 4 bereitstellt werden, um die verzögerte Initialisierung in verschiedenen Szenarien zu ermöglichen.  
  
|Typ|**Beschreibung**|  
|---------|----------------------|  
|<xref:System.Lazy%601>|Eine Wrapperklasse, die die Semantik für die verzögerte Initialisierung für jede Klassenbibliothek oder jeden benutzerdefinierten Typ bereitstellt.|  
|<xref:System.Threading.ThreadLocal%601>|Ist mit <xref:System.Lazy%601> vergleichbar, außer dass dieser Typ die Semantik für die verzögerte Initialisierung auf threadlokaler Basis bereitstellt.  Jeder Thread hat Zugriff auf einen eigenen eindeutigen Wert.|  
|<xref:System.Threading.LazyInitializer>|Stellt erweiterte `static`\-Methoden \(`Shared` in Visual Basic\) für die verzögerte Initialisierung von Objekten ohne den Mehraufwand einer Klasse bereit.|  
  
## Grundlegende verzögerte Initialisierung  
 Um einen Typ mit verzögerter Initialisierung zu definieren, z. B. `MyType`, verwenden Sie `Lazy<MyType>` \(`Lazy(Of MyType)` in Visual Basic\), wie im folgenden Beispiel gezeigt.  Wenn kein Delegat im <xref:System.Lazy%601>\-Konstruktor übergeben wird, wird der umschlossene Typ mit <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> erstellt, wenn erstmals auf die Werteigenschaft zugegriffen wird.  Wenn der Typ nicht über einen Standardkonstruktor verfügt, wird eine Laufzeitausnahme ausgelöst.  
  
 Im folgenden Beispiel wird angenommen, dass `Orders` eine Klasse ist, die ein Array von aus einer Datenbank abgerufenen `Order`\-Objekten enthält.  Ein `Customer`\-Objekt enthält eine Instanz von `Orders`, aber abhängig von Benutzeraktionen sind die Daten aus dem `Orders`\-Objekt möglicherweise nicht erforderlich.  
  
 [!code-csharp[Lazy#1](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#1)]
 [!code-vb[Lazy#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#1)]  
  
 Sie können auch einen Delegaten im <xref:System.Lazy%601>\-Konstruktor übergeben, der eine bestimmte Konstruktorüberladung zur Erstellungszeit für den umschlossenen Typ aufruft, und beliebige andere Initialisierungsschritte ausführen, die erforderlich sind, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[Lazy#2](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#2)]
 [!code-vb[Lazy#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#2)]  
  
 Nachdem das verzögerte Objekt erstellt wurde, wird keine Instanz von `Orders` erstellt, bis erstmals auf die <xref:System.Lazy%601.Value%2A>\-Eigenschaft der Lazy\-Variable zugegriffen wird.  Beim erstem Zugriff wird der umschlossene Typ erstellt und zurückgegeben und für einen zukünftigen Zugriff gespeichert.  
  
 [!code-csharp[Lazy#3](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#3)]
 [!code-vb[Lazy#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#3)]  
  
 Ein <xref:System.Lazy%601>\-Objekt gibt immer das gleiche Objekt oder den gleichen Wert zurück, mit dem es initialisiert wurde.  Die <xref:System.Lazy%601.Value%2A>\-Eigenschaft ist daher schreibgeschützt.  Wenn <xref:System.Lazy%601.Value%2A> einen Verweistyp speichert, können Sie ihm kein neues Objekt zuweisen. \(Sie können jedoch den Wert der festlegbaren öffentlichen Felder und Eigenschaften des Verweistyps ändern.\) Wenn <xref:System.Lazy%601.Value%2A> einen Werttyp speichert, können Sie dessen Wert nicht ändern.  Trotzdem können Sie eine neue Variable erstellen, indem Sie den variablen Konstruktor erneut mit neuen Argumenten aufrufen.  
  
 [!code-csharp[Lazy#4](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#4)]
 [!code-vb[Lazy#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#4)]  
  
 Die neue verzögerte Instanz instanziiert – wie die vorherige – das `Orders`\-Objekt erst, wenn erstmals auf die <xref:System.Lazy%601.Value%2A>\-Eigenschaft zugegriffen wird.  
  
### Threadsichere Initialisierung  
 Standardmäßig sind <xref:System.Lazy%601>\-Objekte threadsicher.  Das heißt, wenn der Konstruktor die Art der Threadsicherheit nicht angibt, sind die von diesem erstellten <xref:System.Lazy%601>\-Objekte threadsicher.  In Multithreadszenarien wird die <xref:System.Lazy%601.Value%2A>\-Eigenschaft eines threadsicheren <xref:System.Lazy%601>\-Objekts durch den ersten Thread, der auf die Eigenschaft zugreift, für alle nachfolgenden Zugriffe auf allen Threads initialisiert, und alle Threads verwenden die gleichen Daten.  Daher ist es nicht relevant, welcher Thread das Objekt initialisiert, und Racebedingungen haben keine Auswirkung.  
  
> [!NOTE]
>  Sie können diese Konsistenz auf Fehlerzustände erweitern, indem Sie eine Zwischenspeicherung für Ausnahmen verwenden.  Weitere Informationen finden Sie im nächsten Abschnitt, [Ausnahmen in verzögerten Objekten](../../../docs/framework/performance/lazy-initialization.md#ExceptionsInLazyObjects).  
  
 Das folgende Beispiel zeigt, dass die gleiche `Lazy<int>`\-Instanz über den gleichen Wert für drei separate Threads verfügt.  
  
 [!code-csharp[Lazy#8](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#8)]
 [!code-vb[Lazy#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#8)]  
  
 Wenn Sie separate Daten für jeden Thread benötigen, verwenden Sie den <xref:System.Threading.ThreadLocal%601>\-Typ, wie weiter unten in diesem Thema beschrieben.  
  
 Einige <xref:System.Lazy%601>\-Konstruktoren besitzen den booleschen Parameter `isThreadSafe`, mit dem angegeben wird, ob auf die <xref:System.Lazy%601.Value%2A>\-Eigenschaft von mehreren Threads zugegriffen wird.  Wenn Sie beabsichtigen, dass nur von einem Thread auf die Eigenschaft zugegriffen wird, übergeben Sie `false`, um einen bescheidenen Leistungsvorteil zu erhalten.  Wenn von mehreren Threads auf die Eigenschaft zugriffen werden soll, übergeben Sie `true`, um die <xref:System.Lazy%601>\-Instanz anzuweisen, die Racebedingungen, unter denen ein Thread eine Ausnahme zur Initialisierungszeit auslöst, ordnungsgemäß zu behandeln.  
  
 Einige <xref:System.Lazy%601>\-Konstruktoren besitzen einen <xref:System.Threading.LazyThreadSafetyMode>\-Parameter mit dem Namen `mode`.  Diese Konstruktoren stellen einen zusätzlichen Threadsicherheitsmodus bereit.  Die folgende Tabelle zeigt, wie die Threadsicherheit eines <xref:System.Lazy%601>\-Objekts von Konstruktorparametern betroffen ist, die Threadsicherheit angeben.  Jeder Konstruktor verfügt höchstens über einen solchen Parameter.  
  
|Threadsicherheit des Objekts|`mode`\-Parameter von `LazyThreadSafetyMode`|Boolescher `isThreadSafe`\-Parameter|Keine Threadsicherheitsparameter|  
|----------------------------------|--------------------------------------------------|------------------------------------------|--------------------------------------|  
|Vollständig threadsicher; nur ein Thread versucht jeweils, den Wert zu initialisieren.|<xref:System.Threading.LazyThreadSafetyMode>|`true`|Ja.|  
|Nicht threadsicher.|<xref:System.Threading.LazyThreadSafetyMode>|`false`|Nicht zutreffend.|  
|Vollständig threadsicher; Threads befinden sich im Racezustand, um den Wert zu initialisieren.|<xref:System.Threading.LazyThreadSafetyMode>|Nicht zutreffend.|Nicht zutreffend.|  
  
 Wie die Tabelle zeigt, ist das Angeben von <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> für den `mode`\-Parameter mit dem Angeben von `true` für den `isThreadSafe`\-Parameter gleichwertig, und das Angeben von <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> ist mit dem Angeben von `false` gleichwertig.  
  
 Wenn Sie <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> angeben, können mehrere Threads versuchen, die <xref:System.Lazy%601>\-Instanz zu initialisieren.  Nur ein Thread kann unter dieser Racebedingung gewinnen, und alle anderen Threads empfangen den Wert, der vom erfolgreichen Thread initialisiert wurde.  Wenn während der Initialisierung eine Ausnahme für einen Thread ausgelöst wird, empfängt der betreffende Thread nicht den vom erfolgreichen Thread festgelegten Wert.  Ausnahmen werden nicht zwischengespeichert, deshalb kann ein späterer Versuch, auf die <xref:System.Lazy%601.Value%2A>\-Eigenschaft zuzugreifen, zu einer erfolgreichen Initialisierung führen.  Dies weicht von der Weise ab, in der Ausnahmen in anderen Modi behandelt werden, wie im folgenden Abschnitt beschrieben.  Weitere Informationen finden Sie unter der <xref:System.Threading.LazyThreadSafetyMode>\-Enumeration.  
  
<a name="ExceptionsInLazyObjects"></a>   
## Ausnahmen in verzögerten Objekten  
 Wie zuvor angegeben, gibt ein <xref:System.Lazy%601>\-Objekt immer das gleiche Objekt oder den gleichen Wert zurück, mit dem es initialisiert wurde. Daher ist die <xref:System.Lazy%601.Value%2A>\-Eigenschaft schreibgeschützt.  Wenn Sie die Zwischenspeicherung für Ausnahmen aktivieren, gilt diese Unveränderlichkeit auch für das Ausnahmeverhalten.  Wenn die Zwischenspeicherung für Ausnahmen für ein verzögert initialisiertes Objekt aktiviert ist und in der Initialisierungsmethode beim ersten Zugriff auf die <xref:System.Lazy%601.Value%2A>\-Eigenschaft eine Ausnahme ausgelöst wird, wird die gleiche Ausnahme bei jedem nachfolgenden Versuch, auf die <xref:System.Lazy%601.Value%2A>\-Eigenschaft zuzugreifen, ausgelöst.  Dies bedeutet, dass der Konstruktor des umschlossenen Typs nie erneut aufgerufen wird, auch nicht in Multithreadszenarien.  Daher kann das <xref:System.Lazy%601>\-Objekt nicht bei einem Zugriff eine Ausnahme auslösen und bei einem nachfolgenden Zugriff einen Wert zurückgeben.  
  
 Die Zwischenspeicherung für Ausnahmen wird aktiviert, sobald Sie einen beliebigen <xref:System.Lazy%601?displayProperty=fullName>\-Konstruktor verwenden, der eine Initialisierungsmethode akzeptiert \(`valueFactory`\-Parameter\). Beispielsweise wird sie aktiviert, wenn Sie den `Lazy(T)(Func(T))`\-Konstruktor verwenden.  Wenn der Konstruktor auch einen <xref:System.Threading.LazyThreadSafetyMode>\-Wert \(`mode`\-Parameter\) erwartet, geben Sie <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> oder <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> an.  Durch das Angeben einer Initialisierungsmethode wird die Zwischenspeicherung für Ausnahmen für diese beiden Modi aktiviert.  Die Initialisierungsmethode kann sehr einfach sein.  Sie kann z. B. den Standardkonstruktor für `T` aufrufen: `new Lazy<Contents>(() => new Contents(), mode)` in C\# oder `New Lazy(Of Contents)(Function() New Contents())` in Visual Basic.  Wenn Sie einen <xref:System.Lazy%601?displayProperty=fullName>\-Konstruktor verwenden, der keine Initialisierungsmethode angibt, werden Ausnahmen, die vom Standardkonstruktor für `T` ausgelöst werden, nicht zwischengespeichert.  Weitere Informationen finden Sie unter der <xref:System.Threading.LazyThreadSafetyMode>\-Enumeration.  
  
> [!NOTE]
>  Wenn Sie ein <xref:System.Lazy%601>\-Objekt mit dem Wert `false` im `isThreadSafe`\-Konstruktorparameter oder dem Wert <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> im `mode`\-Konstruktorparameter erstellen, müssen Sie von einem einzelnen Thread aus auf das <xref:System.Lazy%601>\-Objekt zugreifen oder eine eigene Synchronisierung bereitstellen.  Dies gilt für alle Aspekte des Objekts, einschließlich der Zwischenspeicherung für Ausnahmen.  
  
 Wie im vorherigen Abschnitt erwähnt, werden Ausnahmen von <xref:System.Lazy%601>\-Objekten unterschiedlich behandelt, die durch Angeben von <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> erstellt wurden.  In <xref:System.Threading.LazyThreadSafetyMode> können mehrere Threads um das Initialisieren der <xref:System.Lazy%601>\-Instanz konkurrieren.  In diesem Fall werden Ausnahmen nicht zwischengespeichert, und Versuche, auf die <xref:System.Lazy%601.Value%2A>\-Eigenschaft zugreifen, können fortgesetzt werden, bis die Initialisierung erfolgreich ist.  
  
 In der folgenden Tabelle wird die Steuerung der Zwischenspeicherung für Ausnahmen durch die <xref:System.Lazy%601>\-Konstruktoren zusammengefasst.  
  
|Konstruktor|Threadsicherheitsmodus|Initialisierungsmethode wird verwendet|Ausnahmen werden zwischengespeichert|  
|-----------------|----------------------------|--------------------------------------------|------------------------------------------|  
|Lazy\(T\)\(\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|nein|nein|  
|Lazy\(T\)\(Func\(T\)\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|ja|ja|  
|Lazy\(T\)\(Boolean\)|`True` \(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) oder `false` \(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|nein|nein|  
|Lazy\(T\)\(Func\(T\), Boolean\)|`True` \(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) oder `false` \(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|ja|ja|  
|Lazy\(T\)\(LazyThreadSafetyMode\)|Benutzerdefiniert|nein|nein|  
|Lazy\(T\)\(Func\(T\), LazyThreadSafetyMode\)|Benutzerdefiniert|ja|Nein, wenn der Benutzer <xref:> System.Threading.LazyThreadSafetyMode.PublicationOnly?qualifyHint=False&autoUpgrade=True angibt, andernfalls Ja.|  
  
## Implementieren einer verzögert initialisierten Eigenschaft  
 Um eine öffentliche Eigenschaft mit verzögerter Initialisierung zu implementieren, definieren Sie das dahinter liegende Feld der Eigenschaft als <xref:System.Lazy%601>, und geben Sie die <xref:System.Lazy%601.Value%2A>\-Eigenschaft des `get`\-Accessors der Eigenschaft zurück.  
  
 [!code-csharp[Lazy#5](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#5)]
 [!code-vb[Lazy#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#5)]  
  
 Die <xref:System.Lazy%601.Value%2A>\-Eigenschaft ist schreibgeschützt; daher besitzt die Eigenschaft, die sie verfügbar macht, keinen `set`\-Accessor.  Wenn eine von einem <xref:System.Lazy%601>\-Objekt unterstützte Lese\-\/Schreibeigenschaft erforderlich ist, muss der `set` ein neues <xref:System.Lazy%601>\-Objekt erstellen und diesen dem Sicherungsspeicher zuweisen.  Der `set`\-Accessor muss einen Lambda\-Ausdruck erstellen, der den neuen, an den `set`\-Accessor übergebenen Eigenschaftswert zurückgibt, und diesen Lambda\-Ausdruck an den Konstruktor für das neue <xref:System.Lazy%601>\-Objekt übergeben.  Der nächste Zugriff der <xref:System.Lazy%601.Value%2A>\-Eigenschaft verursacht eine Initialisierung des neuen <xref:System.Lazy%601>, und die zugehörige <xref:System.Lazy%601.Value%2A>\-Eigenschaft gibt danach den neuen Wert zurück, der der Eigenschaft zugewiesen wurde.  Der Grund für diese komplizierte Anordnung besteht darin, dass der in <xref:System.Lazy%601> integrierte Multithreadingschutz beibehalten wird.  Andernfalls müssten die Eigenschaftenaccessoren den ersten von der <xref:System.Lazy%601.Value%2A>\-Eigenschaft zurückgegebenen Wert zwischenspeichern und nur den zwischengespeicherten Wert ändern, und Sie müssten für diesen Zweck eigenen threadsicheren Code schreiben.  Aufgrund der zusätzlichen Initialisierungen, die von einer durch ein <xref:System.Lazy%601>\-Objekt unterstützten Lese\-\/Schreibeigenschaft angefordert wird, ist die Leistung dann möglicherweise nicht akzeptabel.  Je nach Szenario kann zudem eine zusätzliche Koordination erforderlich sein, um Racebedingungen zwischen Settern und Gettern zu vermeiden.  
  
## Threadlokale verzögerte Initialisierung  
 In einigen Multithreadszenarien möchten Sie den einzelnen Threads möglicherweise eigene private Daten zuweisen.  Solche Daten werden als *threadlokale Daten* bezeichnet.  In .NET Framework, Version 3.5 und früher, können Sie das `ThreadStatic`\-Attribut auf eine statische Variable anwenden, um diese threadlokal zu machen.  Das Verwenden des `ThreadStatic`\-Attributs kann jedoch zu subtilen Fehlern führen.  So können sogar einfache Initialisierungsanweisungen beispielsweise bewirken, dass die Variable nur auf dem ersten Thread, der darauf zugreift, initialisiert wird, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[Lazy#6](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#6)]
 [!code-vb[Lazy#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#6)]  
  
 Auf allen anderen Threads wird die Variable mit dem Standardwert \(0\) initialisiert.  Als Alternative können Sie in .NET Framework, Version 4, mithilfe des <xref:System.Threading.ThreadLocal%601?displayProperty=fullName>\-Typs eine instanzbasierte, threadlokale Variable erstellen, die auf allen Threads vom <xref:System.Action%601>\-Delegaten initialisiert wird, den Sie bereitstellen.  Im folgenden Beispiel wird für alle Threads, die auf `counter` zugreifen, der Startwert "1" angezeigt.  
  
 [!code-csharp[Lazy#7](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#7)]
 [!code-vb[Lazy#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#7)]  
  
 <xref:System.Threading.ThreadLocal%601> umschließt sein Objekt auf die gleiche Weise wie <xref:System.Lazy%601>, aber es bestehen die folgenden wesentlichen Unterschiede:  
  
-   Jeder Thread initialisiert die threadlokale Variable durch Verwendung eigener privater Daten, auf die nicht von anderen Threads aus zugegriffen werden kann.  
  
-   <xref:System.Threading.ThreadLocal%601.Value%2A?displayProperty=fullName> ist eine Lese\-\/Schreibeigenschaft und kann beliebig oft geändert werden.  Dies kann sich auf Ausnahmeverteilung auswirken. So kann beispielsweise ein `get`\-Vorgang eine Ausnahme auslösen, aber der nächste kann den Wert erfolgreich initialisieren.  
  
-   Wenn kein Initialisierungsdelegat bereitgestellt wird, initialisiert <xref:System.Threading.ThreadLocal%601> seinen umschlossenen Typ mit dem Standardwert des Typs.  In dieser Hinsicht ist <xref:System.Threading.ThreadLocal%601> mit dem <xref:System.ThreadStaticAttribute>\-Attribut konsistent.  
  
 Im folgenden Beispiel wird veranschaulicht, dass jeder Thread, der auf die `ThreadLocal<int>`\-Instanz zugreift, eine eigene eindeutige Kopie der Daten abruft.  
  
 [!code-csharp[Lazy#9](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#9)]
 [!code-vb[Lazy#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#9)]  
  
## Threadlokale Variablen in Parallel.For und ForEach  
 Wenn Sie die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\-Methode oder die <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>\-Methode verwenden, um Datenquellen parallel zu durchlaufen, können Sie die Überladungen verwenden, die über eine integrierte Unterstützung für threadlokale Daten verfügen.  In diesen Methoden wird die Threadlokalität mit lokalen Delegaten erreicht, um Daten zu erstellen, darauf zuzugreifen und zu bereinigen.  Weitere Informationen finden Sie unter [How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) und [How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md).  
  
## Verwenden der verzögerten Initialisierung für Szenarien mit geringem Mehraufwand  
 In Szenarien, in denen eine große Anzahl von Objekten verzögert initialisiert werden muss, erfordert das Umschließen jedes Objekt in einem <xref:System.Lazy%601>\-Objekt ggf. zu viel Arbeitsspeicher oder zu viele Computerressourcen.  Oder es könnten strenge Anforderungen dahingehend bestehen, wie die verzögerte Initialisierung verfügbar gemacht wird.  In solchen Fällen können Sie die `static`\-Methoden \(`Shared` in Visual Basic\) der <xref:System.Threading.LazyInitializer?displayProperty=fullName>\-Klasse verwenden, um jedes Objekt verzögert zu initialisieren, ohne dass es von einer Instanz von <xref:System.Lazy%601> umschlossen wird.  
  
 Im folgenden Beispiel wird angenommen, dass kein ganzes `Orders`\-Objekt von einem <xref:System.Lazy%601>\-Objekt umschlossen wird. Stattdessen werden einzelne `Order`\-Objekte verzögert initialisiert, wenn dies erforderlich ist.  
  
 [!code-csharp[Lazy#10](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#10)]
 [!code-vb[Lazy#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#10)]  
  
 Beachten Sie, dass in diesem Beispiel die Initialisierungsprozedur für jede Iteration der Schleife aufgerufen wird.  In Multithreadszenarien ist der erste Thread, der die Initialisierungsprozedur aufruft, der Thread, dessen Wert für alle Threads sichtbar ist.  Spätere Threads rufen auch die Initialisierungsprozedur auf, aber ihre Ergebnisse werden nicht verwendet.  Wenn diese Art von potenzieller Racebedingung nicht akzeptabel ist, verwenden Sie die Überladung von <xref:System.Threading.LazyInitializer.EnsureInitialized%2A?displayProperty=fullName>, die ein boolesches Argument und ein Synchronisierungsobjekt akzeptiert.  
  
## Siehe auch  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [How to: Perform Lazy Initialization of Objects](../../../docs/framework/performance/how-to-perform-lazy-initialization-of-objects.md)
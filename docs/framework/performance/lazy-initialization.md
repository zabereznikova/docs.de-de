---
title: Verzögerte Initialisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, introduction
ms.assetid: 56b4ae5c-4745-44ff-ad78-ffe4fcde6b9b
ms.openlocfilehash: 4f2b585dded6e20bb604f623217c6d1f1505c097
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180569"
---
# <a name="lazy-initialization"></a>Verzögerte Initialisierung
*Verzögerte Initialisierung* eines Objekts bedeutet, dass seine Erstellung bis zur ersten Verwendung verzögert wird. (Für dieses Thema sind die Begriffe *verzögerte Initialisierung* und *verzögerte Instanziierung* gleichbedeutend.) Die verzögerte Initialisierung wird in erster Linie verwendet, um die Leistung zu verbessern, verschwenderische Berechnungen zu vermeiden und den Programmspeicherbedarf zu reduzieren. Die folgenden Szenarios sind die häufigsten:  
  
- Sie verfügen über ein Objekt, dessen Erstellung teuer ist und das möglicherweise nicht vom Programm verwendet wird. Angenommen, in Ihrem Speicher befindet sich ein `Customer`-Objekt mit einer `Orders`-Eigenschaft, die ein großes Array aus `Order`-Objekten enthält, das zur Initialisierung eine Datenbankverbindung benötigt. Fordert der Benutzer nie die Anzeige des Orders-Objekts oder die Verwendung der Daten in einer Berechnung an, ist es nicht notwendig, Systemspeicher oder Berechnungszyklen für seine Erstellung zu verwenden. Systemressourcen können geschont werden, wenn Sie die verzögerte Initialisierung für das `Orders`-Objekt mithilfe von `Lazy<Orders>` deklarieren, solange das Objekt nicht verwendet wird.  
  
- Sie verfügen über ein Objekt, dessen Erstellung teuer ist und das daher erst erstellt werden soll, wenn andere teure Vorgänge abgeschlossen sind. Angenommen, das Programm lädt beim Start mehrere Objektinstanzen, von denen allerdings nur einige sofort benötigt werden. Hier kann die Startleistung des Programms verbessert werden, indem die Initialisierung der nicht benötigten Objekte verzögert wird, bis die benötigten Objekte erstellt wurden.  
  
 Sie können für die verzögerte Initialisierung Ihren eigenen Code schreiben. Es ist jedoch empfehlenswert, stattdessen <xref:System.Lazy%601> zu verwenden. <xref:System.Lazy%601> und die zugehörigen verwandten Typen unterstützen auch die Threadsicherheit und stellen eine konsistente Richtlinie zur Ausnahmeweitergabe bereit.  
  
 In der folgenden Tabelle werden die Typen aufgelistet, die .NET Framework Version 4 bereitstellt, um die verzögerte Initialisierung in verschiedenen Szenarios zu aktivieren.  
  
|type|Beschreibung|  
|----------|-----------------|  
|<xref:System.Lazy%601>|Eine Wrapperklasse, die die Semantik für verzögerte Initialisierung für jeden Klassenbibliotheks- oder benutzerdefinierten Typ bereitstellt.|  
|<xref:System.Threading.ThreadLocal%601>|Ähnlich wie <xref:System.Lazy%601>, außer dass die Semantik für verzögerte Initialisierung threadlokal bereitgestellt wird. Jeder Thread hat Zugriff auf seinen eigenen eindeutigen Wert.|  
|<xref:System.Threading.LazyInitializer>|Stellt erweiterte `static`-Methoden (`Shared` in Visual Basic) für die verzögerte Initialisierung von Objekten bereit ohne den Mehraufwand einer Klasse.|  
  
## <a name="basic-lazy-initialization"></a>Grundlegende verzögerte Initialisierung  
 Verwenden Sie `Lazy<MyType>` (`Lazy(Of MyType)` in Visual Basic) wie in folgendem Beispiel gezeigt, um einen Typ mit verzögerter Initialisierung, z.B. `MyType`, zu definieren. Wird im <xref:System.Lazy%601>-Konstruktor kein Delegat übergeben, wird der umschlossene Typ mithilfe von <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> beim ersten Zugriff auf die Value-Eigenschaft erstellt. Wenn der Typ keinen parameterlosen Konstruktor hat, wird eine Laufzeitausnahme ausgelöst.  
  
 Im folgenden Beispiel wird angenommen, dass `Orders` eine Klasse mit einem Array aus `Order`-Objekten ist, die aus einer Datenbank abgerufen wurden. Ein `Customer`-Objekt enthält eine Instanz von `Orders`, je nach Benutzeraktion werden die Daten aus dem `Orders`-Objekt jedoch möglicherweise nicht benötigt.  
  
 [!code-csharp[Lazy#1](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#1)]
 [!code-vb[Lazy#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#1)]  
  
 Sie können im <xref:System.Lazy%601>-Konstruktor auch einen Delegaten übergeben, der bei der Erstellung eine bestimmte Konstruktorüberladung für den umschlossenen Typ aufruft. Außerdem können Sie die weiteren erforderlichen Initialisierungsschritte wie im folgenden Beispiel gezeigt ausführen.  
  
 [!code-csharp[Lazy#2](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#2)]
 [!code-vb[Lazy#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#2)]  
  
 Nachdem das Lazy-Objekt erstellt wurde, wird erst eine Instanz von `Orders` erstellt, wenn auf die <xref:System.Lazy%601.Value%2A>-Eigenschaft der Lazy-Variable zum ersten Mal zugegriffen wird. Beim ersten Zugriff wird der umschlossene Typ erstellt, zurückgegeben und für einen späteren Zugriff gespeichert.  
  
 [!code-csharp[Lazy#3](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#3)]
 [!code-vb[Lazy#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#3)]  
  
 Ein <xref:System.Lazy%601>-Objekt gibt immer das gleiche Objekt oder den gleichen Wert zurück, mit dem es initialisiert wurde. Daher besitzt die <xref:System.Lazy%601.Value%2A>-Eigenschaft nur einen Lesezugriff. Wenn <xref:System.Lazy%601.Value%2A> einen Verweistyp speichert, können Sie ihm kein neues Objekt zuweisen. (Sie können jedoch den Wert der festsetzbaren öffentlichen Felder und Eigenschaften ändern.) Wenn <xref:System.Lazy%601.Value%2A> ein Werttyp gespeichert wird, können Sie dessen Wert nicht ändern. Sie können jedoch eine neue Variable erstellen, indem Sie den Variablenkonstruktor erneut mit neuen Argumenten aufrufen.  
  
 [!code-csharp[Lazy#4](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#4)]
 [!code-vb[Lazy#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#4)]  
  
 Die neue verzögerte Instanz instanziiert das `Orders`-Objekt wie die vorherige erst, wenn auf die <xref:System.Lazy%601.Value%2A>-Eigenschaft erstmals zugegriffen wird.  
  
### <a name="thread-safe-initialization"></a>Threadsichere Initialisierung  
 Standardmäßig sind <xref:System.Lazy%601>-Objekte threadsicher. Wird im Konstruktor die Art der Threadsicherheit nicht angegeben, sind die erstellten <xref:System.Lazy%601>-Objekte daher threadsicher. In Multithreadszenarios initialisiert der erste Thread, der auf die <xref:System.Lazy%601.Value%2A>-Eigenschaft eines threadsicheren <xref:System.Lazy%601>-Objekts zugreift, die Eigenschaft für jeden nachfolgenden Zugriff auf allen Threads. Alle Threads nutzen dieselben Daten. Daher spielt es keine Rolle, welcher Thread das Objekt initialisiert. Auch Racebedingungen haben keine Auswirkung.  
  
> [!NOTE]
> Diese Konsistenz kann durch das Zwischenspeichern von Ausnahmen auf Fehlerbedingungen erweitert werden. Weitere Informationen finden Sie im folgenden Abschnitt [Ausnahmen bei verzögerten Objekten](lazy-initialization.md#ExceptionsInLazyObjects).  
  
 Das folgende Beispiel verdeutlicht, dass die gleiche `Lazy<int>`-Instanz über den gleichen Wert für drei separate Threads verfügt.  
  
 [!code-csharp[Lazy#8](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#8)]
 [!code-vb[Lazy#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#8)]  
  
 Wenn Sie separate Daten für jeden Thread benötigen, verwenden Sie wie weiter unten beschrieben den <xref:System.Threading.ThreadLocal%601>-Typ.  
  
 Einige <xref:System.Lazy%601>-Konstruktoren verfügen über einen booleschen Parameter mit dem Namen `isThreadSafe`, der angibt, ob auf die <xref:System.Lazy%601.Value%2A>-Eigenschaft von mehreren Threads zugegriffen wird. Wenn Sie von nur einem Thread auf die Eigenschaft zugreifen möchten, übergeben Sie `false` für einen moderaten Leistungsvorteil. Wenn Sie von mehreren Threads auf die Eigenschaft zugreifen möchten, übergeben Sie `true`, um die <xref:System.Lazy%601>-Instanz anzuweisen, die Racebedingungen ordnungsgemäß zu behandeln, von denen ein Thread bei der Initialisierung eine Ausnahme auslöst.  
  
 Einige <xref:System.Lazy%601>-Konstruktoren verfügen über einen <xref:System.Threading.LazyThreadSafetyMode>-Parameter mit dem Namen `mode`. Diese Konstruktoren stellen einen zusätzlichen Threadsicherheitsmodus bereit. Entnehmen Sie der folgenden Tabelle, wie die Threadsicherheit eines <xref:System.Lazy%601>-Objekts von den Konstruktorparametern beeinflusst wird, die die Threadsicherheit angeben. Jeder Konstruktor verfügt über höchstens einen solchen Parameter.  
  
|Threadsicherheit des Objekts|`LazyThreadSafetyMode``mode` Parameter|Boolescher Parameter `isThreadSafe`|Keine Threadsicherheitsparameter|  
|---------------------------------|---------------------------------------------|--------------------------------------|---------------------------------|  
|Vollständig threadsicher; nur ein Thread versucht jeweils, den Wert zu initialisieren.|<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>|`true`|Ja.|  
|Nicht threadsicher.|<xref:System.Threading.LazyThreadSafetyMode.None>|`false`|Nicht zutreffend|  
|Vollständig threadsicher; Threads befinden sich im Race, um den Wert zu initialisieren.|<xref:System.Threading.LazyThreadSafetyMode.PublicationOnly>|Nicht zutreffend|Nicht zutreffend|  
  
 Die Tabelle verdeutlicht, dass die Angabe von <xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?displayProperty=nameWithType> für den `mode`-Parameter der Angabe von `true` für den `isThreadSafe`-Parameter entspricht, ebenso wie die Angabe von <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType> der Angabe von `false`.  
  
 Die Angabe von <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly?displayProperty=nameWithType> ermöglicht mehreren Threads, die Initialisierung der <xref:System.Lazy%601>-Instanz zu versuchen. Nur ein Thread kann unter dieser Racebedingung gewinnen. Alle anderen Threads empfangen den Wert, der vom erfolgreichen Thread initialisiert wurde. Wird während der Initialisierung für einen Thread eine Ausnahme ausgelöst, empfängt dieser Thread nicht den vom erfolgreichen Thread festgelegten Wert. Da Ausnahmen nicht zwischengespeichert werden, kann ein nachfolgender Versuch, auf die <xref:System.Lazy%601.Value%2A>-Eigenschaft zuzugreifen, zu einer erfolgreichen Initialisierung führen. Darin besteht ein Unterschied zur Behandlung von Ausnahmen in anderen Modi, die im folgenden Abschnitt beschrieben werden. Weitere Informationen finden Sie unter der <xref:System.Threading.LazyThreadSafetyMode>-Enumeration.  
  
<a name="ExceptionsInLazyObjects"></a>
## <a name="exceptions-in-lazy-objects"></a>Ausnahmen bei verzögerten Objekten  
 Wie weiter oben erwähnt gibt ein <xref:System.Lazy%601>-Objekt immer das gleiche Objekt oder den gleichen Wert zurück, mit dem es initialisiert wurde. Daher verfügt die <xref:System.Lazy%601.Value%2A>-Eigenschaft nur über einen Lesezugriff. Wird das Zwischenspeichern von Ausnahmen aktiviert, wird diese Unveränderlichkeit auch auf das Ausnahmeverhalten erweitert. Wenn für ein lazy-initialisiertes Objekt die Ausnahmezwischenspeicherung aktiviert ist <xref:System.Lazy%601.Value%2A> und beim ersten Zugriff auf die Eigenschaft eine <xref:System.Lazy%601.Value%2A> Ausnahme von der Initialisierungsmethode ausgelöst wird, wird dieselbe Ausnahme bei jedem nachfolgenden Versuch, auf die Eigenschaft zuzugreifen, ausgelöst. Anders ausgedrückt wird der Konstruktor des umschlossenen Typs selbst in Multithreadszenarios niemals erneut aufgerufen. Aus diesem Grund kann das <xref:System.Lazy%601>-Objekt nicht bei einem Zugriff eine Ausnahme auslösen und bei einem nachfolgenden Zugriff einen Wert zurückgeben.  
  
 Das Zwischenspeichern von Ausnahmen wird bei der Verwendung eines beliebigen <xref:System.Lazy%601?displayProperty=nameWithType>-Konstruktors aktiviert, der eine Initialisierungsmethode erfordert (`valueFactory`-Parameter). So wird es beispielsweise aktiviert, wenn Sie den `Lazy(T)(Func(T))`-Konstruktor verwenden. Erfordert der Konstruktor auch einen <xref:System.Threading.LazyThreadSafetyMode>-Wert (`mode`-Parameter), geben Sie <xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?displayProperty=nameWithType> oder <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType> an. Durch die Angabe einer Initialisierungsmethode wird das Zwischenspeichern von Ausnahmen für diese beiden Modi aktiviert. Die Initialisierungsmethode kann sehr einfach sein. Es kann z. B. den `T`parameterlosen Konstruktor für : `new Lazy<Contents>(() => new Contents(), mode)` in C- oder `New Lazy(Of Contents)(Function() New Contents())` in Visual Basic aufrufen. Wenn Sie einen <xref:System.Lazy%601?displayProperty=nameWithType>-Konstruktor verwenden, der keine Initialisierungsmethode angibt, werden vom parameterlosen Konstruktor für `T` ausgelöste Ausnahmen nicht zwischengespeichert. Weitere Informationen finden Sie unter der <xref:System.Threading.LazyThreadSafetyMode>-Enumeration.  
  
> [!NOTE]
> Wenn der `isThreadSafe`-Konstruktorparameter beim Erstellen eines <xref:System.Lazy%601>-Objekts auf `false` festgelegt ist oder der `mode`-Konstruktorparameter auf <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType>, müssen Sie auf das <xref:System.Lazy%601>-Objekt von einem einzelnen Thread zugreifen oder eine eigene Synchronisierung bereitstellen. Dies gilt für alle Aspekte des Objekts, einschließlich dem Zwischenspeichern von Ausnahmen.  
  
 Wie im vorherigen Abschnitt erwähnt, behandeln durch Angabe von <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly?displayProperty=nameWithType> erstellte <xref:System.Lazy%601>-Objekte Ausnahmen unterschiedlich. Mit <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly> können mehrere Threads um die Initialisierung der <xref:System.Lazy%601>-Instanz konkurrieren. In diesem Fall werden Ausnahmen nicht zwischengespeichert. Die Versuche, auf die <xref:System.Lazy%601.Value%2A>-Eigenschaft zuzugreifen, können fortgesetzt werden, bis die Initialisierung erfolgreich ist.  
  
 In der folgenden Tabelle werden die Steuerungsmethoden für das Zwischenspeichern von Ausnahmen durch <xref:System.Lazy%601>-Konstruktoren zusammengefasst.  
  
|Konstruktor|Threadsicherheitsmodus|Verwendet die Initialisierungsmethode|Ausnahmen werden zwischengespeichert|  
|-----------------|------------------------|--------------------------------|---------------------------|  
|Lazy(T)()|(<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>)|Nein |Nein |  
|Lazy(T)(Func(T))|(<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>)|Ja|Ja|  
|Lazy(T)(Boolean)|`True` (<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>) oder `false` (<xref:System.Threading.LazyThreadSafetyMode.None>)|Nein |Nein |  
|Lazy(T)(Func(T), Boolean)|`True` (<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>) oder `false` (<xref:System.Threading.LazyThreadSafetyMode.None>)|Ja|Ja|  
|Lazy(T)(LazyThreadSafetyMode)|Vom Benutzer angegeben|Nein |Nein |  
|Lazy(T)(Func(T), LazyThreadSafetyMode)|Vom Benutzer angegeben|Ja|Nein, wenn der Benutzer <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly> angibt; andernfalls ja.|  
  
## <a name="implementing-a-lazy-initialized-property"></a>Implementieren einer Eigenschaft mit verzögerter Initialisierung  
 Definieren Sie zum Implementieren einer öffentlichen Eigenschaft mit der verzögerten Initialisierung das Unterstützungsfeld der Eigenschaft als <xref:System.Lazy%601>, und geben Sie die <xref:System.Lazy%601.Value%2A>-Eigenschaft des `get`-Accessors der Eigenschaft zurück.  
  
 [!code-csharp[Lazy#5](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#5)]
 [!code-vb[Lazy#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#5)]  
  
 Die <xref:System.Lazy%601.Value%2A>-Eigenschaft besitzt nur Lesezugriff. Daher verfügt die Eigenschaft, die sie verfügbar macht, über keinen `set`-Accessor. Ist eine Lese-/Schreibeigenschaft erforderlich, die durch ein <xref:System.Lazy%601>-Objekt gesichert wird, muss der `set`-Accessor ein neues <xref:System.Lazy%601>-Objekt erstellen und dem Sicherungsspeicher zuweisen. Der `set`-Accessor muss einen Lambdaausdruck erstellen, der den an den `set`-Accessor übergebenen neuen Eigenschaftswert zurückgibt. Dieser Lambdaausdruck muss anschließend an den Konstruktor für das neue <xref:System.Lazy%601>-Objekt übergeben werden. Der nächste Zugriff auf die <xref:System.Lazy%601.Value%2A>-Eigenschaft führt zur Initialisierung des neuen <xref:System.Lazy%601>. Die zugehörige <xref:System.Lazy%601.Value%2A>-Eigenschaft gibt danach den neuen Wert zurück, der der Eigenschaft zugewiesen wurde. Der Grund für diese komplizierte Gestaltung besteht darin, dass der in <xref:System.Lazy%601> integrierte Multithreadingschutz beibehalten werden soll. Andernfalls müssten die Eigenschaftenaccessoren den ersten von der <xref:System.Lazy%601.Value%2A>-Eigenschaft zurückgegebenen Wert zwischenspeichern und nur den zwischengespeicherten Wert ändern. Dafür müssten Sie Ihren eigenen threadsicheren Code schreiben. Aufgrund der zusätzlichen Initialisierungen, die von einer durch ein <xref:System.Lazy%601>-Objekt gesicherten Lese-/Schreibeigenschaft angefordert werden, ist die Leistung möglicherweise nicht akzeptabel. Darüber hinaus kann je nach Szenario eine zusätzliche Koordinierung erforderlich sein, um Racebedingungen zwischen Setter und Getter zu vermeiden.  
  
## <a name="thread-local-lazy-initialization"></a>Threadlokale verzögerte Initialisierung  
 In einigen Multithreadszenarios möchten Sie jedem Thread möglicherweise eigene private Daten zuweisen. Diese Daten werden *threadlokale Daten* genannt. Bis .NET Framework Version 3.5 konnte das `ThreadStatic`-Attribut auf eine statische Variable angewendet werden, um aus ihr eine threadlokale Variable zu machen. Die Anwendung des `ThreadStatic`-Attributs kann jedoch geringfügige Fehler verursachen. Selbst grundlegende Initialisierungsanweisungen führen z.B. dazu, dass die Variable wie im folgenden Beispiel gezeigt nur für den ersten Thread initialisiert wird, der auf sie zugreift.  
  
 [!code-csharp[Lazy#6](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#6)]
 [!code-vb[Lazy#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#6)]  
  
 Für alle anderen Threads wird die Variable mit ihrem Standardwert (0) initialisiert. In .NET Framework Version 4 kann der <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>-Typ alternativ dazu zum Erstellen einer instanzbasierten, threadlokalen Variable verwendet werden, die für alle Threads mit dem von Ihnen bereitgestellten <xref:System.Action%601>-Delegaten initialisiert wird. Im folgenden Beispiel erhalten alle Threads, die auf `counter` zugreifen, den Startwert 1.  
  
 [!code-csharp[Lazy#7](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#7)]
 [!code-vb[Lazy#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#7)]  
  
 <xref:System.Threading.ThreadLocal%601> umschließt sein Objekt auf fast die gleiche Weise wie <xref:System.Lazy%601>, mit folgenden entscheidenden Unterschieden:  
  
- Jeder Thread initialisiert die threadlokale Variable mit seinen eigenen privaten Daten, auf die von anderen Threads nicht zugegriffen werden kann.  
  
- Die <xref:System.Threading.ThreadLocal%601.Value%2A?displayProperty=nameWithType>-Eigenschaft verfügt über Lese-/Schreibzugriff und kann beliebig oft geändert werden. Dies kann sich auf die Ausnahmeweitergabe auswirken: So kann ein `get`-Vorgang z.B. eine Ausnahme auslösen, während der nächste den Wert erfolgreich initialisiert.  
  
- <xref:System.Threading.ThreadLocal%601> initialisiert seinen umschlossenen Typ mit dem Standardwert des Typs, wenn kein Initialisierungsdelegat bereitgestellt wird. In dieser Hinsicht ist <xref:System.Threading.ThreadLocal%601> mit dem <xref:System.ThreadStaticAttribute>-Attribut konsistent.  
  
 Das folgende Beispiel verdeutlicht, dass jeder auf die `ThreadLocal<int>`-Instanz zugreifende Thread eine eigene eindeutige Kopie der Daten erhält.  
  
 [!code-csharp[Lazy#9](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#9)]
 [!code-vb[Lazy#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#9)]  
  
## <a name="thread-local-variables-in-parallelfor-and-foreach"></a>Threadlokale Variablen in Parallel.For und ForEach  
 Beim parallelen Durchlaufen von Datenquellen mit den Methoden <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> oder <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> können Sie Überladungen mit integrierter Unterstützung für threadlokale Daten verwenden. Bei diesen Methoden wird die Threadlokalität mithilfe von lokalen Delegaten erzielt, um die Daten zu erstellen, auf sie zuzugreifen und sie zu bereinigen. Weitere Informationen finden Sie unter [How to: Write a Parallel.For Loop with Thread-Local Variables (Vorgehensweise: Schreiben einer Parallel.For-Schleife mit threadlokalen Variablen)](../../standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) und [How to: Write a Parallel.ForEach Loop with Partition-Local Variables (Vorgehensweise: Schreiben einer Parallel.ForEach-Schleife mit partitionslokalen Variablen)](../../standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md).  
  
## <a name="using-lazy-initialization-for-low-overhead-scenarios"></a>Verwenden der verzögerten Initialisierung für Szenarios mit geringem Mehraufwand  
 In Szenarios mit einer großen Anzahl von Objekten, die verzögert initialisiert werden sollen, würde das Umschließen jedes einzelnen Objekts mit einem <xref:System.Lazy%601> möglicherweise zu viel Arbeitsspeicher oder zu viele Computerressourcen erfordern. Möglicherweise bestehen auch strenge Anforderungen an die Art, wie die verzögerte Initialisierung verfügbar gemacht wird. In diesen Fällen können Sie die `static`-Methoden (`Shared` in Visual Basic) der <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>-Klasse zur Initialisierung jedes Objekts verwenden, ohne es mit einer Instanz von <xref:System.Lazy%601> zu umschließen.  
  
 Im folgenden Beispiel wird angenommen, dass einzelne `Order`-Objekte nur nach Bedarf verzögert initialisiert werden, anstatt ein ganzes `Orders`-Objekt mit einem <xref:System.Lazy%601>-Objekt zu umschließen.  
  
 [!code-csharp[Lazy#10](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#10)]
 [!code-vb[Lazy#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#10)]  
  
 Beachten Sie, dass in diesem Beispiel die Initialisierungsprozedur bei jeder Iteration der Schleife aufgerufen wird. In Multithreadszenarios ist der erste Thread, der die Initialisierungsprozedur aufruft, derjenige, dessen Wert für alle Threads sichtbar ist. Zwar rufen auch spätere Threads die Initialisierungsprozedur auf, doch werden ihre Ergebnisse nicht verwendet. Ist diese Art von potenzieller Racebedingung nicht akzeptabel, verwenden Sie die Überladung von <xref:System.Threading.LazyInitializer.EnsureInitialized%2A?displayProperty=nameWithType>, die ein boolesches Argument und ein Synchronisierungsobjekt erfordert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Grundlagen des verwalteten Threadings](../../standard/threading/managed-threading-basics.md)
- [Threads und Threading](../../standard/threading/threads-and-threading.md)
- [Task Parallel Library (TPL)](../../standard/parallel-programming/task-parallel-library-tpl.md)
- [How to: Perform Lazy Initialization of Objects (Vorgehensweise: Verzögerte Initialisierung von Objekten)](how-to-perform-lazy-initialization-of-objects.md)

---
title: 'Vorgehensweise: Definieren einer generischen Methode mit Reflektionsausgabe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic methods
- generics [.NET Framework], dynamic types
ms.assetid: 93892fa4-90b3-4ec4-b147-4bec9880de2b
ms.openlocfilehash: d16f6728b01583fe3ffb8d892522f3892444c537
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130173"
---
# <a name="how-to-define-a-generic-method-with-reflection-emit"></a>Vorgehensweise: Definieren einer generischen Methode mit Reflektionsausgabe

Im ersten Verfahren wird veranschaulicht, wie eine einfache generische Methode mit zwei Typparametern erstellt wird und wie auf die Typparameter Klasseneinschränkungen, Schnittstelleneinschränkungen und besonderen Einschränkungen angewendet werden.

Im zweiten Verfahren wird veranschaulicht, wie der Methodentext ausgegeben wird und wie mithilfe der Typparameter der generischen Methode Instanzen generischer Typen erstellt und deren Methoden aufgerufen werden.

Im dritten Verfahren wird das Aufrufen der generischen Methode veranschaulicht.

> [!IMPORTANT]
> Eine Methode ist nicht generisch, weil sie zu einem generischen Typ gehört und die Typparameter dieses Typs verwendet. Eine Methode ist nur dann generisch, wenn sie über eine eigene Typparameterliste verfügt. Eine generische Methode kann zu einem nicht generischen Typ gehören, wie im vorliegenden Beispiel. Ein Beispiel für eine nicht generische Methode für einen generischen Typ finden Sie unter [Vorgehensweise: Definieren eines generischen Typs mit Reflektionsausgabe](how-to-define-a-generic-type-with-reflection-emit.md).

### <a name="to-define-a-generic-method"></a>So definieren Sie eine generische Methode

1. Sie sollten sich zunächst einmal klarmachen, wie eine in einer hoch entwickelten Sprache geschriebene generische Methode aussieht. Der folgende Code befindet sich, zusammen mit dem Code zum Aufrufen der generischen Methode, im Beispielcode für dieses Thema. Die Methode verfügt über die beiden Typparameter `TInput` und `TOutput`, wobei der zweite ein Referenztyp sein muss (`class`), einen parameterlosen Konstruktor (`new`) aufweisen und `ICollection(Of TInput)` (`ICollection<TInput>` in C#) implementieren muss. Dank dieser Schnittstelleneinschränkung kann die <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>-Methode zum Hinzufügen von Elementen zur `TOutput`-Auflistung verwendet werden, die von der Methode erstellt wird. Die Methode verfügt über einen formalen Parameter `input`, der ein Array von `TInput` ist. Die Methode erstellt eine Auflistung vom Typ `TOutput` und kopiert die Elemente von `input` in die Auflistung.

    [!code-csharp[GenericMethodHowTo#20](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#20)]
    [!code-vb[GenericMethodHowTo#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#20)]

2. Definieren Sie eine dynamische Assembly und ein dynamisches Modul, um den Typ aufzunehmen, dem die generische Methode angehört. Die Assembly enthält in diesem Fall nur ein Modul mit der Bezeichnung `DemoMethodBuilder1`. Der Modulname setzt sich aus dem Assemblynamen und einer Erweiterung zusammen. In diesem Beispiel wird die Assembly ausgeführt und auf einem Datenträger gespeichert, daher wird <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType> angegeben. Mithilfe von [Ildasm.exe (IL-Disassembler)](../tools/ildasm-exe-il-disassembler.md) können Sie DemoMethodBuilder1.dll untersuchen und mit dem in Schritt 1 gezeigten Microsoft Intermediate Language (MSIL)-Code für die Methode vergleichen.

    [!code-csharp[GenericMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#2)]
    [!code-vb[GenericMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#2)]

3. Definieren Sie den Typ, zu dem die generische Methode gehört. Der Typ muss nicht generisch sein. Eine generische Methode kann sowohl zu einem generischen als auch zu einem nicht generischen Typ gehören. Der Typ ist hier eine Klasse, ist nicht generisch und trägt die Bezeichnung `DemoType`.

    [!code-csharp[GenericMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#3)]
    [!code-vb[GenericMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#3)]

4. Definieren Sie die generische Methode. Wenn die Typen der formalen Parameter einer generischen Methode durch generische Typparameter der generischen Methode angegeben werden, definieren Sie die Methode mithilfe der <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%28System.String%2CSystem.Reflection.MethodAttributes%29>-Methodenüberladung. Da die generischen Typparameter der Methode noch nicht definiert sind, können Sie die Typen der formalen Parameter der Methode im Aufruf von <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%2A> nicht angeben. In diesem Beispiel trägt die Methode die Bezeichnung `Factory`. Die Methode ist öffentlich und `static` (`Shared` in Visual Basic).

    [!code-csharp[GenericMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#4)]
    [!code-vb[GenericMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#4)]

5. Definieren Sie die generischen Typparameter von `DemoMethod`, indem Sie ein Array von Zeichenfolgen, das die Namen der Parameter enthält, an die <xref:System.Reflection.Emit.MethodBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>-Methode übergeben. Dadurch wird die Methode zu einer generischen Methode. Im folgenden Code wird `Factory` zu einer generischen Methode mit den beiden Typparametern `TInput` und `TOutput` gemacht. Um den Code verständlicher zu gestalten, werden gleichnamige Variablen erstellt, die die <xref:System.Reflection.Emit.GenericTypeParameterBuilder>-Objekte aufnehmen, die die beiden Typparameter darstellen.

    [!code-csharp[GenericMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#5)]
    [!code-vb[GenericMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#5)]

6. Fügen Sie den Typparametern bei Bedarf besondere Einschränkungen hinzu. Besondere Einschränkungen werden mit der <xref:System.Reflection.Emit.GenericTypeParameterBuilder.SetGenericParameterAttributes%2A>-Methode hinzugefügt. In diesem Beispiel wird `TOutput` durch eine Einschränkung zu einem Referenztyp, der über einen parameterlosen Konstruktor verfügt.

    [!code-csharp[GenericMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#6)]
    [!code-vb[GenericMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#6)]

7. Fügen Sie den Typparametern bei Bedarf Klassen- und Schnittstelleneinschränkungen hinzu. In diesem Beispiel wird der Typparameter `TOutput` auf Typen eingeschränkt, die die `ICollection(Of TInput)`-Schnittstelle (`ICollection<TInput>` in C#) implementieren. Dadurch kann die <xref:System.Collections.Generic.ICollection%601.Add%2A>-Methode zum Hinzufügen von Elementen verwendet werden.

    [!code-csharp[GenericMethodHowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#7)]
    [!code-vb[GenericMethodHowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#7)]

8. Definieren Sie die formalen Parameter der Methode mithilfe der <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A>-Methode. In diesem Beispiel verfügt die `Factory`-Methode über einen Parameter, ein Array von `TInput`. Dieser Typ wird durch aufrufen der <xref:System.Type.MakeArrayType%2A>-Methode für <xref:System.Reflection.Emit.GenericTypeParameterBuilder> erstellt, der `TInput` darstellt. Das Argument von <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A> ist ein Array von <xref:System.Type>-Objekten.

    [!code-csharp[GenericMethodHowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#8)]
    [!code-vb[GenericMethodHowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#8)]

9. Definieren Sie den Rückgabetyp für die Methode mithilfe der <xref:System.Reflection.Emit.MethodBuilder.SetReturnType%2A>-Methode. In diesem Beispiel wird eine Instanz von `TOutput` zurückgegeben.

    [!code-csharp[GenericMethodHowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#9)]
    [!code-vb[GenericMethodHowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#9)]

10. Geben Sie den Methodentext mithilfe von <xref:System.Reflection.Emit.ILGenerator> aus. Weitere Einzelheiten hierzu finden Sie im zugehörigen Verfahren zum Ausgeben des Methodentexts.

    > [!IMPORTANT]
    > Wenn Sie Aufrufe von Methoden generischer Typen ausgeben und es sich bei den Typargumenten dieser Typen um Typparameter der generischen Methode handelt, müssen Sie über die `static`-Methodenüberladungen <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29>, <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29> und <xref:System.Reflection.Emit.TypeBuilder.GetField%28System.Type%2CSystem.Reflection.FieldInfo%29> der <xref:System.Reflection.Emit.TypeBuilder>-Klasse erstellte Formulare der Methoden abrufen. Dies wird im zugehörigen Verfahren zum Ausgeben von Methodentext veranschaulicht.

11. Vervollständigen Sie den Typ, der die Methode enthält, und speichern Sie die Assembly. Im zugehörigen Verfahren zum Aufrufen der generischen Methode werden zwei Möglichkeiten zum Aufrufen der vollständigen Methode veranschaulicht.

    [!code-csharp[GenericMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#14)]
    [!code-vb[GenericMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#14)]

<a name="procedureSection1"></a>

### <a name="to-emit-the-method-body"></a>So geben Sie den Methodentext aus

1. Rufen Sie einen Code-Generator ab, und deklarieren Sie lokale Variablen und Bezeichnungen. Die lokalen Variablen werden mit der <xref:System.Reflection.Emit.ILGenerator.DeclareLocal%2A>-Methode deklariert. Die `Factory`-Methode verfügt über vier lokale Variablen: `retVal` nimmt den neuen `TOutput` auf, der von der Methode zurückgegeben wird, `ic` nimmt den `TOutput` bei der Umwandlung in `ICollection(Of TInput)` (`ICollection<TInput>` in C#) auf, `input` nimmt das Eingabearray von `TInput`-Objekten auf, und `index` durchläuft das Array. Die Methode enthält auch zwei Bezeichnungen, eine zum Starten der Schleife (`enterLoop`) und eine für den Anfang der Schleife (`loopAgain`), die mit der <xref:System.Reflection.Emit.ILGenerator.DefineLabel%2A>-Methode definiert werden.

    Die Methode lädt zunächst mit dem <xref:System.Reflection.Emit.OpCodes.Ldarg_0>-Opcode ihre Argumente und speichert diese mit dem in dem `input`-Opcode in der lokalen Variable <xref:System.Reflection.Emit.OpCodes.Stloc_S>.

    [!code-csharp[GenericMethodHowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#10)]
    [!code-vb[GenericMethodHowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#10)]

2. Geben Sie Code aus, um mithilfe der generischen Methodenüberladung der `TOutput`-Methode eine Instanz von <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> zu erstellen. Für die Verwendung dieser Überladung muss der angegebene Typ über einen parameterlosen Konstruktor verfügen, daher wird `TOutput` diese Einschränkung hinzugefügt. Erstellen Sie die erstellte generische Methode, indem Sie `TOutput` an <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> übergeben. Geben Sie nach der Ausgabe von Code für den Methodenaufruf mithilfe von `retVal` Code zum Speichern in der lokalen Variable <xref:System.Reflection.Emit.OpCodes.Stloc_S> aus.

    [!code-csharp[GenericMethodHowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#11)]
    [!code-vb[GenericMethodHowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#11)]

3. Geben Sie Code aus, um das neue `TOutput`-Objekt in `ICollection(Of TInput)` umzuwandeln und dieses in der lokalen Variable `ic` zu speichern.

    [!code-csharp[GenericMethodHowTo#31](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#31)]
    [!code-vb[GenericMethodHowTo#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#31)]

4. Rufen Sie eine <xref:System.Reflection.MethodInfo> ab, die die <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>-Methode darstellt. Da diese Methode `ICollection(Of TInput)` (`ICollection<TInput>` in C#) behandelt, muss die für diesen erstellten Typ spezifische `Add`-Methode abgerufen werden. Sie können diese <xref:System.Type.GetMethod%2A> nicht mithilfe der <xref:System.Reflection.MethodInfo>-Methode direkt aus `icollOfTInput` abrufen, da <xref:System.Type.GetMethod%2A> nicht für einen Typ unterstützt wird, der mit einem <xref:System.Reflection.Emit.GenericTypeParameterBuilder> erstellt wurde. Rufen Sie stattdessen <xref:System.Type.GetMethod%2A> für `icoll` auf, der die Definition des generischen Typs für die generische <xref:System.Collections.Generic.ICollection%601>-Schnittstelle enthält. Erzeugen Sie dann mithilfe der <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29>`static`-Methode die <xref:System.Reflection.MethodInfo> für den konstruierten Typ. Im folgenden Code wird dies veranschaulicht.

    [!code-csharp[GenericMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#12)]
    [!code-vb[GenericMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#12)]

5. Geben Sie Code aus, um die `index`-Variable zu initialisieren, indem Sie eine 32-Bit-Ganzzahl 0 laden und diese in der Variablen speichern. Geben Sie Code aus, um zur Bezeichnung `enterLoop` zu verzweigen. Diese Bezeichnung wurde noch nicht markiert, da sie sich in der Schleife befindet. Der Code für die Schleife wird im nächsten Schritt ausgegeben.

    [!code-csharp[GenericMethodHowTo#32](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#32)]
    [!code-vb[GenericMethodHowTo#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#32)]

6. Geben Sie Code für die Schleife aus. Zunächst wird der Anfang der Schleife markiert, indem <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> mit der `loopAgain`-Bezeichnung aufgerufen wird. Verzweigungsanweisungen, die die Bezeichnung verwenden, verzweigen jetzt zu diesem Punkt im Code. Anschließend wird das in `TOutput` umgewandelte `ICollection(Of TInput)`-Objekt auf dem Stapel abgelegt. Es wird zwar nicht sofort benötigt, muss jedoch zum Aufrufen der `Add`-Methode vorhanden sein. Nun werden das Eingabearray auf dem Stapel und die `index`-Variable mit dem aktuellen Index im Array abgelegt. Der <xref:System.Reflection.Emit.OpCodes.Ldelem>-Opcode nimmt den Index und das Array vom Stapel auf und legt das indizierte Arrayelement auf dem Stapel ab. Der Stapel ist jetzt für das Aufrufen der <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>-Methode bereit, die die Auflistung und das neue Element vom Stapel aufnimmt und das Element zur Auflistung hinzufügt.

    Der Rest des Codes in der Schleife erhöht schrittweise den Index und Tests, um festzustellen, ob die Schleife beendet ist: Der Index und das 32-Bit-Integer 1 werden auf dem Stapel abgelegt und hinzugefügt, wobei die Summe auf dem Stapel bleibt; die Summe wird in `index` gespeichert. <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> wird aufgerufen, um diesen Punkt als Einstiegspunkt für die Schleife festzulegen. Der Index wird erneut geladen. Das Eingabearray wird auf dem Stapel abgelegt und <xref:System.Reflection.Emit.OpCodes.Ldlen> wird ausgegeben, um seine Länge abzurufen. Nun befinden sich der Index und die Länge auf dem Stapel, und <xref:System.Reflection.Emit.OpCodes.Clt> wird ausgegeben, um sie zu vergleichen. Wenn der Index kleiner als die Länge ist, verzweigt <xref:System.Reflection.Emit.OpCodes.Brtrue_S> zurück zum Anfang der Schleife.

    [!code-csharp[GenericMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#13)]
    [!code-vb[GenericMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#13)]

7. Geben Sie Code aus, um das `TOutput`-Objekt auf dem Stapel abzulegen und die Methode zu beenden. Die lokalen Variablen `retVal` und `ic` enthalten beide Verweise auf die neue `TOutput`. `ic` wird nur für den Zugriff auf die <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>-Methode verwendet.

    [!code-csharp[GenericMethodHowTo#33](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#33)]
    [!code-vb[GenericMethodHowTo#33](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#33)]

<a name="procedureSection2"></a>

### <a name="to-invoke-the-generic-method"></a>So rufen Sie die generische Methode auf

1. `Factory` ist eine generische Methodendefinition. Um sie aufzurufen, müssen Sie ihren generischen Typparametern Typen zuweisen. Verwenden Sie hierfür die <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>-Methode. Im folgenden Code wird eine konstruierte generische Methode erstellt. Dabei wird <xref:System.String> für `TInput` und `List(Of String)` (`List<string>` in C#) für `TOutput` angegeben, und es wird eine Zeichenfolgendarstellung der Methode angezeigt.

    [!code-csharp[GenericMethodHowTo#21](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#21)]
    [!code-vb[GenericMethodHowTo#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#21)]

2. Um die Methode spät gebunden aufzurufen, verwenden Sie die <xref:System.Reflection.MethodBase.Invoke%2A>-Methode. Im folgenden Code wird ein Array von <xref:System.Object> erstellt, dessen einziges Element ein Array von Zeichenfolgen ist, und als Argumentliste für die generische Methode übergeben. Der erste Parameter von <xref:System.Reflection.MethodBase.Invoke%2A> ist ein NULL-Verweis, da die Methode `static` ist. Der Rückgabewert wird in `List(Of String)` umgewandelt, und sein erstes Element wird angezeigt.

    [!code-csharp[GenericMethodHowTo#22](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#22)]
    [!code-vb[GenericMethodHowTo#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#22)]

3. Um die Methode mithilfe eines Delegaten aufzurufen, benötigen Sie einen Delegaten, der der Signatur der konstruierten generischen Methode entspricht. Dafür erstellen Sie ganz einfach einen generischen Delegaten. Im folgenden Code wird mithilfe der `D`-Methodenüberladung eine Instanz des im Beispielcode definierten generischen Delegaten <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Reflection.MethodInfo%29?displayProperty=nameWithType> erstellt und aufgerufen. Delegaten bieten eine bessere Leistung als spät gebundene Aufrufe.

    [!code-csharp[GenericMethodHowTo#23](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#23)]
    [!code-vb[GenericMethodHowTo#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#23)]

4. Die ausgegebene Methode kann auch von einem Programm aufgerufen werden, das auf die gespeicherte Assembly verweist.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird ein nicht generischer Typ `DemoType` mit der generischen Methode `Factory` erstellt. Diese Methode verfügt über zwei generische Typparameter, `TInput` zum Angeben eines Eingabetyps und `TOutput` zum Angeben eines Ausgabetyps. Der `TOutput`-Typparameter wird durch Implementieren von `ICollection<TInput>` (`ICollection(Of TInput)` in Visual Basic) zu einem Referenztyp eingeschränkt, der über einen parameterlosen Konstruktor verfügt.

Die Methode verfügt über einen formalen Parameter, der ein Array von `TInput` ist. Die Methode gibt eine Instanz von `TOutput` zurück, die alle Elemente des Eingabearrays enthält. `TOutput` kann ein beliebiger generischer Auflistungstyp sein, der die generische <xref:System.Collections.Generic.ICollection%601>-Schnittstelle implementiert.

Bei der Codeausführung wird die dynamische Assembly als DemoGenericMethod1.dll gespeichert. Sie kann mit [Ildasm.exe (IL-Disassembler)](../tools/ildasm-exe-il-disassembler.md) untersucht werden.

> [!NOTE]
> Wenn Sie das Ausgeben von Code erlernen möchten, empfiehlt es sich, ein Visual Basic-, C#- oder Visual C++-Programm zu schreiben, das die Aufgabe ausführt, die Sie ausgeben möchten, und anschließend anhand eines Disassemblers den vom Compiler generierten MSIL-Code zu untersuchen.

Das Codebeispiel enthält Quellcode, der der ausgegebenen Methode entspricht. Die ausgegebene Methode wird spät gebunden anhand eines generischen Delegaten aufgerufen, der im Codebeispiel deklariert ist.

[!code-csharp[GenericMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#1)]
[!code-vb[GenericMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.Emit.MethodBuilder>
- [How to: Definieren eines generischen Typs mit Reflektionsausgabe](how-to-define-a-generic-type-with-reflection-emit.md)

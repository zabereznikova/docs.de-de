---
title: Verwenden von Delegaten – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], how to use
ms.assetid: 99a2fc27-a32e-4a34-921c-e65497520eec
ms.openlocfilehash: dcc73aba738d6296a44c48aad8b66cd6fc7f4a7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77448438"
---
# <a name="using-delegates-c-programming-guide"></a>Verwenden von Delegaten (C#-Programmierhandbuch)

Ein [Delegat](../../language-reference/builtin-types/reference-types.md) ist ein Typ, der ähnlich einem Funktionszeiger in C und C++ eine Methode sicher kapselt. Im Gegensatz zu C-Funktionszeigern sind Delegate objektorientiert, typsicher und sicher. Der Typ eines Delegaten wird durch den Namen des Delegaten definiert. Im folgenden Beispiel wird ein Delegat mit dem Namen `Del` deklariert, der eine Methode kapseln kann, die eine [Zeichenfolge](../../language-reference/builtin-types/reference-types.md) als Argument übernimmt und [void](../../language-reference/builtin-types/void.md) zurückgibt:

[!code-csharp[csProgGuideDelegates#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#21)]

Ein Delegatobjekt wird normalerweise durch Angabe des Namens der Methode, die der Delegat umschließt, oder mit einer [anonymen Funktion](../statements-expressions-operators/anonymous-functions.md) erstellt. Sobald ein Delegat instanziiert ist, wird vom Delegaten ein Methodenaufruf an den Delegaten an diese Methode übergeben. Die vom Aufrufer an den Delegaten übergebenen Parameter werden an die Methode übergeben, und der Rückgabewert von der Methode wird ggf. durch den Delegaten an den Aufrufer zurückgegeben. Dies wird als Aufrufen des Delegaten bezeichnet. Ein instanziierter Delegat kann wie die eingeschlossene Methode selbst aufgerufen werden. Beispiel:

[!code-csharp[csProgGuideDelegates#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#22)]  

[!code-csharp[csProgGuideDelegates#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#23)]

Delegattypen werden von der <xref:System.Delegate>-Klasse im .NET Framework abgeleitet. Delegattypen sind [versiegelt](../../language-reference/keywords/sealed.md) – von Ihnen kann nicht abgeleitet werden – und es ist nicht möglich benutzerdefinierte Klassen von <xref:System.Delegate> abzuleiten. Da der instanziierte Delegat ein Objekt ist, kann er als Parameter übergeben oder einer Eigenschaft zugewiesen werden. Dies ermöglicht es einer Methode, einen Delegaten als Parameter zu akzeptieren und den Delegaten zu einem späteren Zeitpunkt aufzurufen. Dies wird als asynchroner Rückruf bezeichnet und ist eine häufig verwendete Methode, um einen Aufrufer darüber zu benachrichtigen, dass ein langer Prozess abgeschlossen wurde. Wenn ein Delegat auf diese Weise verwendet wird, benötigt der Code, der den Delegaten verwendet, keine Kenntnisse über die Implementierung der verwendeten Methode. Die Funktion ähnelt den bereitgestellten Kapselungsschnittstellen.

Ein weiterer häufiger Einsatzbereich von Rückrufen ist die Definition einer benutzerdefinierten Vergleichsmethode und die Übergabe dieses Delegaten an eine Sortiermethode. Dadurch kann der Code des Aufrufers Teil des Sortieralgorithmus werden. Im folgenden Beispiel wird der Typ `Del` als Parameter verwendet:

[!code-csharp[csProgGuideDelegates#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#24)]

Sie können anschließend den oben erstellten Delegaten an diese Methode übergeben:

[!code-csharp[csProgGuideDelegates#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#25)]

woraufhin die folgende Ausgabe auf der Konsole angezeigt wird:

```console
The number is: 3
```

Wenn Sie den Delegaten als Abstraktion verwenden, muss `MethodWithCallback` die Konsole nicht direkt aufrufen, d. h., bei der Entwicklung muss keine Konsole berücksichtigt werden. `MethodWithCallback` bereitet einfach eine Zeichenfolge vor und übergibt sie an eine andere Methode. Dies ist besonders leistungsstark, da eine delegierte Methode eine beliebige Anzahl Parameter verwenden kann.

Wenn ein Delegat erstellt wurde, um eine Instanzenmethode zu umschließen, verweist der Delegat sowohl auf die Instanz als auch auf die Methode. Ein Delegat kennt nicht den Instanzentyp, abgesehen von der umschlossenen Methode, sodass ein Delegat auf jede Art von Objekt verweisen kann, sofern es eine Methode für das Objekt gibt, die mit der Signatur des Delegaten übereinstimmt. Wenn ein Delegat erstellt wurde, um eine statische Methode zu umschließen, verweist er nur auf die Methode. Betrachten Sie hierzu die folgenden Deklarationen:

[!code-csharp[csProgGuideDelegates#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#26)]

Zusammen mit der zuvor dargestellten statischen `DelegateMethod` verfügen Sie jetzt über drei Methoden, die von einer `Del`-Instanz umschlossen werden können.

Ein Delegat kann bei Aufruf mehr als eine Methode aufrufen. Dies wird als Multicasting bezeichnet. Um der Liste an Methoden des Delegaten, sprich der Aufrufliste, eine weitere Methode hinzuzufügen, müssen lediglich zwei Delegaten mithilfe der Additions- oder Additionszuweisungsoperatoren ('+' oder '+=') hinzugefügt werden. Beispiel:

[!code-csharp[csProgGuideDelegates#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#27)]

Zu diesem Zeitpunkt enthält `allMethodsDelegate` drei Methoden in der Aufrufliste: `Method1`, `Method2` und `DelegateMethod`. Die ursprünglichen drei Delegaten, `d1`, `d2` und `d3`, bleiben unverändert. Wenn `allMethodsDelegate` aufgerufen wird, werden alle drei Methoden nacheinander aufgerufen. Wenn der Delegat Verweisparameter verwendet, wird der Verweis wiederum nacheinander an jede der drei Methoden übergeben, und alle Änderungen einer Methode sind für die nächste Methode sichtbar. Wenn eine der Methoden eine Ausnahme auslöst, die nicht innerhalb der Methode abgefangen wird, wird diese Ausnahme an den Aufrufer des Delegaten übergeben und keine der nachfolgenden Methoden in der Aufrufliste wird aufgerufen. Wenn der Delegat über einen Rückgabewert und/oder out-Parameter verfügt, gibt er den Rückgabewert und die Parameter der letzten aufgerufenen Methode zurück. Um eine Methode aus der Aufrufliste zu entfernen, verwenden Sie die [Subtraktions- oder Subtraktionszuweisungsoperatoren](../../language-reference/operators/subtraction-operator.md) (`-` oder `-=`). Beispiel:

[!code-csharp[csProgGuideDelegates#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#28)]

Da Delegattypen von `System.Delegate` abgeleitet werden, können die Methoden und Eigenschaften, die durch diese Klasse definiert werden, für den Delegaten aufgerufen werden. Beispiel: Schreiben Sie Folgendes, um die Anzahl der Methoden in der Aufrufliste eines Delegaten zu ermitteln:

[!code-csharp[csProgGuideDelegates#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#29)]

Delegaten mit mehr als einer Methode in der Aufrufliste werden von <xref:System.MulticastDelegate>, einer Unterklasse von `System.Delegate`, abgeleitet. Der obige Code funktioniert in jedem Fall, da beide Klassen `GetInvocationList` unterstützen.

Multicastdelegaten werden ausgiebig bei der Ereignisbehandlung verwendet. Ereignisquellobjekte senden Ereignisbenachrichtigungen an Empfängerobjekte, die für den Erhalt dieses Ereignisses registriert wurden. Um sich für ein Ereignis zu registrieren, erstellt der Empfänger eine Methode zur Behandlung des Ereignisses, dann erstellt er einen Delegaten für die Methode und übergibt den Delegaten an die Ereignisquelle. Die Quelle ruft den Delegaten auf, wenn das Ereignis eintritt. Der Delegat ruft dann die Ereignisbehandlungsmethode für den Empfänger auf und übermittelt die Ereignisdaten. Der Delegattyp für ein bestimmtes Ereignis wird von der Ereignisquelle definiert. Weitere Informationen finden Sie unter [Ereignisse](../events/index.md).

Beim Vergleichen von zwei unterschiedlichen zugewiesenen Typen zur Kompilierzeit kommt es zu einem Kompilierungsfehler. Falls die Delegatinstanzen statisch vom Typ `System.Delegate` sind, dann ist der Vergleich zulässig, gibt jedoch zur Laufzeit "False" zurück. Beispiel:

[!code-csharp[csProgGuideDelegates#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#30)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Delegaten](./index.md)
- [Verwenden von Varianz bei Delegaten](../concepts/covariance-contravariance/using-variance-in-delegates.md)
- [Varianz bei Delegaten](../concepts/covariance-contravariance/variance-in-delegates.md)
- [Verwenden von Varianz für die generischen Delegaten Func und Action](../concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
- [Ereignisse](../events/index.md)

---
title: Verwenden von Delegaten (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: delegates [C#], how to use
ms.assetid: 99a2fc27-a32e-4a34-921c-e65497520eec
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cef62448388299f310fa26ecb632485b6538c032
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-delegates-c-programming-guide"></a>Verwenden von Delegaten (C#-Programmierhandbuch)
Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) ist ein Typ, der ähnlich einem Funktionszeiger in C und C++ eine Methode sicher kapselt. Im Gegensatz zu C-Funktionszeigern sind Delegate objektorientiert, typsicher und sicher. Der Typ eines Delegaten wird durch den Namen des Delegaten definiert. Im folgenden Beispiel wird ein Delegat mit dem Namen `Del` deklariert, der eine Methode kapseln kann, die eine [Zeichenfolge](../../../csharp/language-reference/keywords/string.md) als Argument übernimmt und [void](../../../csharp/language-reference/keywords/void.md) zurückgibt:  
  
 [!code-csharp[csProgGuideDelegates#21](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_1.cs)]  
  
 Ein Delegatobjekt wird normalerweise durch Angabe des Namens der Methode, die der Delegat umschließt, oder mit einer [anonymen Methode](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) erstellt. Sobald ein Delegat instanziiert ist, wird vom Delegaten ein Methodenaufruf an den Delegaten an diese Methode übergeben. Die vom Aufrufer an den Delegaten übergebenen Parameter werden an die Methode übergeben, und der Rückgabewert von der Methode wird ggf. durch den Delegaten an den Aufrufer zurückgegeben. Dies wird als Aufrufen des Delegaten bezeichnet. Ein instanziierter Delegat kann wie die eingeschlossene Methode selbst aufgerufen werden. Beispiel:  
  
 [!code-csharp[csProgGuideDelegates#22](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_2.cs)]  
  
 [!code-csharp[csProgGuideDelegates#23](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_3.cs)]  
  
 Delegattypen werden von der <xref:System.Delegate>-Klasse im .NET Framework abgeleitet. Delegattypen sind [versiegelt](../../../csharp/language-reference/keywords/sealed.md) – von Ihnen kann nicht abgeleitet werden – und es ist nicht möglich benutzerdefinierte Klassen von <xref:System.Delegate> abzuleiten. Da der instanziierte Delegat ein Objekt ist, kann er als Parameter übergeben oder einer Eigenschaft zugewiesen werden. Dies ermöglicht es einer Methode, einen Delegaten als Parameter zu akzeptieren und den Delegaten zu einem späteren Zeitpunkt aufzurufen. Dies wird als asynchroner Rückruf bezeichnet und ist eine häufig verwendete Methode, um einen Aufrufer darüber zu benachrichtigen, dass ein langer Prozess abgeschlossen wurde. Wenn ein Delegat auf diese Weise verwendet wird, benötigt der Code, der den Delegaten verwendet, keine Kenntnisse über die Implementierung der verwendeten Methode. Die Funktion ähnelt den bereitgestellten Kapselungsschnittstellen.  
  
 Ein weiterer häufiger Einsatzbereich von Rückrufen ist die Definition einer benutzerdefinierten Vergleichsmethode und die Übergabe dieses Delegaten an eine Sortiermethode. Dadurch kann der Code des Aufrufers Teil des Sortieralgorithmus werden. Im folgenden Beispiel wird der Typ `Del` als Parameter verwendet:  
  
 [!code-csharp[csProgGuideDelegates#24](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_4.cs)]  
  
 Sie können anschließend den oben erstellten Delegaten an diese Methode übergeben:  
  
 [!code-csharp[csProgGuideDelegates#25](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_5.cs)]  
  
 woraufhin die folgende Ausgabe auf der Konsole angezeigt wird:  
  
 `The number is: 3`  
  
 Wenn Sie den Delegaten als Abstraktion verwenden, muss `MethodWithCallback` die Konsole nicht direkt aufrufen, d. h., bei der Entwicklung muss keine Konsole berücksichtigt werden. `MethodWithCallback` bereitet einfach eine Zeichenfolge vor und übergibt sie an eine andere Methode. Dies ist besonders leistungsstark, da eine delegierte Methode eine beliebige Anzahl Parameter verwenden kann.  
  
 Wenn ein Delegat erstellt wurde, um eine Instanzenmethode zu umschließen, verweist der Delegat sowohl auf die Instanz als auch auf die Methode. Ein Delegat kennt nicht den Instanzentyp, abgesehen von der umschlossenen Methode, sodass ein Delegat auf jede Art von Objekt verweisen kann, sofern es eine Methode für das Objekt gibt, die mit der Signatur des Delegaten übereinstimmt. Wenn ein Delegat erstellt wurde, um eine statische Methode zu umschließen, verweist er nur auf die Methode. Betrachten Sie hierzu die folgenden Deklarationen:  
  
 [!code-csharp[csProgGuideDelegates#26](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_6.cs)]  
  
 Zusammen mit der zuvor dargestellten statischen `DelegateMethod` verfügen Sie jetzt über drei Methoden, die von einer `Del`-Instanz umschlossen werden können.  
  
 Ein Delegat kann bei Aufruf mehr als eine Methode aufrufen. Dies wird als Multicasting bezeichnet. Um der Liste an Methoden des Delegaten, sprich der Aufrufliste, eine weitere Methode hinzuzufügen, müssen lediglich zwei Delegaten mithilfe der Additions- oder Additionszuweisungsoperatoren ('+' oder '+=') hinzugefügt werden. Beispiel:  
  
 [!code-csharp[csProgGuideDelegates#27](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_7.cs)]  
  
 Zu diesem Zeitpunkt enthält `allMethodsDelegate` drei Methoden in der Aufrufliste: `Method1`, `Method2` und `DelegateMethod`. Die ursprünglichen drei Delegaten, `d1`, `d2` und `d3`, bleiben unverändert. Wenn `allMethodsDelegate` aufgerufen wird, werden alle drei Methoden nacheinander aufgerufen. Wenn der Delegat Verweisparameter verwendet, wird der Verweis wiederum nacheinander an jede der drei Methoden übergeben, und alle Änderungen einer Methode sind für die nächste Methode sichtbar. Wenn eine der Methoden eine Ausnahme auslöst, die nicht innerhalb der Methode abgefangen wird, wird diese Ausnahme an den Aufrufer des Delegaten übergeben und keine der nachfolgenden Methoden in der Aufrufliste wird aufgerufen. Wenn der Delegat über einen Rückgabewert und/oder out-Parameter verfügt, gibt er den Rückgabewert und die Parameter der letzten aufgerufenen Methode zurück. Entfernen Sie eine Methode aus der Aufrufliste, indem Sie den Subtraktions- oder Subtraktionszuweisungsoperator ('-' oder '-=') verwenden. Beispiel:  
  
 [!code-csharp[csProgGuideDelegates#28](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_8.cs)]  
  
 Da Delegattypen von `System.Delegate` abgeleitet werden, können die Methoden und Eigenschaften, die durch diese Klasse definiert werden, für den Delegaten aufgerufen werden. Beispiel: Schreiben Sie Folgendes, um die Anzahl der Methoden in der Aufrufliste eines Delegaten zu ermitteln:  
  
 [!code-csharp[csProgGuideDelegates#29](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_9.cs)]  
  
 Delegaten mit mehr als einer Methode in der Aufrufliste werden von <xref:System.MulticastDelegate>, einer Unterklasse von `System.Delegate`, abgeleitet. Der obige Code funktioniert in jedem Fall, da beide Klassen `GetInvocationList` unterstützen.  
  
 Multicastdelegaten werden ausgiebig bei der Ereignisbehandlung verwendet. Ereignisquellobjekte senden Ereignisbenachrichtigungen an Empfängerobjekte, die für den Erhalt dieses Ereignisses registriert wurden. Um sich für ein Ereignis zu registrieren, erstellt der Empfänger eine Methode zur Behandlung des Ereignisses, dann erstellt er einen Delegaten für die Methode und übergibt den Delegaten an die Ereignisquelle. Die Quelle ruft den Delegaten auf, wenn das Ereignis eintritt. Der Delegat ruft dann die Ereignisbehandlungsmethode für den Empfänger auf und übermittelt die Ereignisdaten. Der Delegattyp für ein bestimmtes Ereignis wird von der Ereignisquelle definiert. Weitere Informationen finden Sie unter [Ereignisse](../../../csharp/programming-guide/events/index.md).  
  
 Beim Vergleichen von zwei unterschiedlichen zugewiesenen Typen zur Kompilierzeit kommt es zu einem Kompilierungsfehler. Falls die Delegatinstanzen statisch vom Typ `System.Delegate` sind, dann ist der Vergleich zulässig, gibt jedoch zur Laufzeit "False" zurück. Zum Beispiel:  
  
 [!code-csharp[csProgGuideDelegates#30](../../../csharp/programming-guide/delegates/codesnippet/CSharp/using-delegates_10.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)  
 [Verwenden von Varianz bei Delegaten](http://msdn.microsoft.com/library/e6acad03-93e0-4efb-a158-8696d5eb4ecf)  
 [Varianz bei Delegaten](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca)  
 [Verwenden von Varianz für die generischen Delegaten Func und Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290)  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)

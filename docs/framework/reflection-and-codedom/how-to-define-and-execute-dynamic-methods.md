---
title: 'Vorgehensweise: Definieren und Ausführen von dynamischen Methoden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
ms.openlocfilehash: 7da9d0bea755b90f73077fcd56558ed66a80e2eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130152"
---
# <a name="how-to-define-and-execute-dynamic-methods"></a>Vorgehensweise: Definieren und Ausführen von dynamischen Methoden
Die folgenden Verfahren zeigen, wie eine einfache dynamische Methode sowie eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist, definiert und ausgeführt werden. Weitere Informationen zu dynamischen Methoden finden Sie in der <xref:System.Reflection.Emit.DynamicMethod>-Klasse und unter [Szenarios für die Reflektionsausgabe mit dynamischen Methoden](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sfk2s47t(v=vs.100)).  
  
### <a name="to-define-and-execute-a-dynamic-method"></a>So definieren und Sie eine dynamische Methode und führen diese aus  
  
1. Deklarieren Sie einen Delegattyp, um die Methode auszuführen. Erwägen Sie, einen generischen Delegaten zu verwenden, um die Anzahl der Delegattypen zu minimieren, die Sie benötigen. Der folgende Code deklariert zwei Delegattypen, die für eine `SquareIt`-Methode verwendet werden könnt. Eine Methode davon ist generisch.  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2. Erstellen Sie ein Array, das die Parametertypen für die dynamische Methode angibt. In diesem Beispiel ist der einzige Parameter ein `int` (`Integer` in Visual Basic), also verfügt das Array nur über ein Element.  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3. Erstellen Sie eine <xref:System.Reflection.Emit.DynamicMethod>. In diesem Beispiel trägt die Methode die Bezeichnung `SquareIt`.  
  
    > [!NOTE]
    > Es ist nicht nötig, den dynamischen Methoden Namen zu geben. Sie können auch nicht nach Namen aufgerufen werden. Mehrere dynamische Methoden können über denselben Namen verfügen. Jedoch erscheint der Name in Aufruflisten und kann für das Debuggen hilfreich sein.  
  
     Der Typ des Rückgabewerts ist als `long` angegeben. Die Methode ist dem Modul zugeordnet, das die `Example`-Klasse besitzt, die den Beispielcode enthält. Jedes geladene Modul kann angegeben werden. Die dynamische Methode verhält sich wie eine `static`-Methode auf Modulebene (`Shared` in Visual Basic).  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4. Geben Sie den Methodentext aus. In diesem Beispiel wird ein <xref:System.Reflection.Emit.ILGenerator>-Objekt zum Ausgeben der Microsoft Intermediate Language (MSIL) verwendet. Alternativ kann ein <xref:System.Reflection.Emit.DynamicILInfo>-Objekt in Kombination mit nicht verwalteten Codegeneratoren verwendet werden, um den Methodentext für eine <xref:System.Reflection.Emit.DynamicMethod> auszugeben.  
  
     Die MSIL lädt in diesem Beispiel das Argument (ein `int`) auf den Stapel, konvertiert es zu `long`, dupliziert `long` und multipliziert die zwei Zahlen. Dadurch verbleibt das quadratische Ergebnis im Stapel, und die Methode muss lediglich wieder zurückspringen.  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5. Erstellen Sie eine Instanz des Delegaten (in Schritt 1 deklariert), der die dynamische Methode durch Aufruf der <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>-Methode darstellt. Durch die Erstellung des Delegaten wird die Methode abgeschlossen und alle weiteren Versuche, die Methode zu ändern, z.B. durch Hinzufügen weiterer MSIL, werden ignoriert. Der folgende Code erstellt den Delegaten und ruft ihn mithilfe eines generischen Delegaten auf.  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### <a name="to-define-and-execute-a-dynamic-method-that-is-bound-to-an-object"></a>So definieren Sie eine dynamische Methode, die an ein Objekt gebunden ist, und führen sie aus  
  
1. Deklarieren Sie einen Delegattyp, um die Methode auszuführen. Erwägen Sie, einen generischen Delegaten zu verwenden, um die Anzahl der Delegattypen zu minimieren, die Sie benötigen. Der folgende Code deklariert einen generischen Delegattyp, der zum Ausführen einer beliebigen Methode mit einem Parameter oder Rückgabewert bzw. einer Methode mit zwei Parametern und einem Rückgabewert verwendet werden kann, falls der Delegat an ein Objekt gebunden ist.  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2. Erstellen Sie ein Array, das die Parametertypen für die dynamische Methode angibt. Wenn der Delegat, der die Methode darstellt, an ein Objekt gebunden ist, muss der erste Parameter mit dem Typ übereinstimmen, an den der Delegat gebunden ist. In diesem Beispiel gibt es zwei Parameter vom Typ `Example` und `int` (`Integer` in Visual Basic).  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3. Erstellen Sie eine <xref:System.Reflection.Emit.DynamicMethod>. In diesem Beispiel hat die Methode keinen Namen. Der Typ des Rückgabewerts ist als `int` (`Integer` in Visual Basic) angegeben. Die Methode hat Zugriff auf die privaten und geschützten Member der `Example`-Klasse.  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4. Geben Sie den Methodentext aus. In diesem Beispiel wird ein <xref:System.Reflection.Emit.ILGenerator>-Objekt zum Ausgeben der Microsoft Intermediate Language (MSIL) verwendet. Alternativ kann ein <xref:System.Reflection.Emit.DynamicILInfo>-Objekt in Kombination mit nicht verwalteten Codegeneratoren verwendet werden, um den Methodentext für eine <xref:System.Reflection.Emit.DynamicMethod> auszugeben.  
  
     Die MSIL lädt in diesem Beispiel das erste Argument, welches eine Instanz der `Example`-Klasse ist, und verwendet es, um den Wert eines privaten Instanzenfelds vom Typ `int` zu laden. Das zweite Argument wird geladen, und zwei Zahlen werden multipliziert. Wenn das Ergebnis größer als `int` ist, wird der Wert abgeschnitten und die wichtigsten Teile verworfen. Die Methode springt zurück und der zurückzugebende Wert befindet sich auf dem Stapel.  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5. Erstellen Sie eine Instanz des Delegaten (in Schritt 1 deklariert), der die dynamische Methode durch Aufruf der <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29>-Methodenüberladung darstellt. Durch die Erstellung des Delegaten wird die Methode abgeschlossen und alle weiteren Versuche, die Methode zu ändern, z.B. durch Hinzufügen weiterer MSIL, werden ignoriert.  
  
    > [!NOTE]
    > Sie können die <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>-Methode mehrfach aufrufen, um die Delegaten zu erstellen, die an andere Instanzen des Zieltyps gebunden sind.  
  
     Der folgende Code bindet die Methode an eine neue Instanz der `Example`-Klasse, deren privates Testfeld auf 42 festgelegt ist. Das heißt, dass jedes Mal, wenn der Delegat aufgerufen wird, die Instanz von `Example` an den ersten Parameter der Methode übergeben wird.  
  
     Der Delegat `OneParameter` wird verwendet, da der erste Parameter der Methode immer die Instanz von `Example` erhält. Wenn der Delegat aufgerufen wird, ist nur der zweite Parameter erforderlich.  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt eine einfache dynamische Methode sowie eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist.  
  
 Die einfache dynamische Methode nimmt ein Argument, einen 32-Bit-Integer und gibt das 64-Bit-Quadrat dieses Integers zurück. Ein generischer Delegat wird zum Aufrufen der Methode verwendet.  
  
 Die zweite dynamische Methode hat zwei Parameter des Typs `Example` und `int` (`Integer` in Visual Basic). Wenn die dynamische Methode erstellt wurde, wird sie mithilfe eines generischen Delegaten, der ein Argument vom Typ `int` besitzt, an eine Instanz von `Example` gebunden. Der Delegat besitzt kein Argument vom Typ `Example`, da der erste Parameter der Methode immer die gebundene Instanz von `Example` erhält. Wenn der Delegat aufgerufen wird, wird nur das `int`-Argument bereitgestellt. Diese dynamische Methode greift auf ein privates Feld der `Example`-Klasse zu und gibt das Produkt des privaten Felds und das `int`-Argument zurück.  
  
 Das Codebeispiel definiert Delegaten, die zum Ausführen dieser Methoden verwendet werden können.  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.Emit.DynamicMethod>
- [Verwenden der Reflektionsausgabe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y322t50(v=vs.100))
- [Szenarios für die Reflektionsausgabe mit dynamischen Methoden](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sfk2s47t(v=vs.100))

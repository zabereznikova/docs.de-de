---
title: 'Vorgehensweise: Definieren eines generischen Typs mit Reflektionsausgabe'
description: Hier erfahren Sie, wie Sie einen generischen Typ mit Reflexionsausgabe definieren. Erstellen Sie einen generischen Typ mit zwei Typparametern, und wenden Sie Klasseneinschränkungen, Schnittstelleneinschränkungen und mehr an.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- generics [.NET Framework], dynamic types
- reflection emit, generic types
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
ms.openlocfilehash: bf308b07bf4b2a863b9825e7c8d9f412bdb6d1b8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559212"
---
# <a name="how-to-define-a-generic-type-with-reflection-emit"></a>Vorgehensweise: Definieren eines generischen Typs mit Reflektionsausgabe
In diesem Thema wird gezeigt, wie ein einfacher generischer Typ mit zwei Typparametern erstellt wird, wie Klasseneinschränkungen, Schnittstelleneinschränkungen und bestimmte Einschränkungen für Typparameter angewandt werden und wie Member erstellt werden, die die Typparameter der Klasse als Parametertypen und Rückgabetypen verwenden.  
  
> [!IMPORTANT]
> Eine Methode ist nicht generisch, weil sie zu einem generischen Typ gehört und die Typparameter dieses Typs verwendet. Eine Methode ist nur dann generisch, wenn sie über eine eigene Typparameterliste verfügt. Die meisten Methoden für generische Typen sind nicht generisch, so auch in diesem Beispiel. Ein Beispiel für die Ausgabe einer generischen Methode finden Sie unter [Vorgehensweise: Definieren einer generischen Methode mit Reflektionsausgabe](how-to-define-a-generic-method-with-reflection-emit.md).  
  
### <a name="to-define-a-generic-type"></a>So definieren Sie einen generischen Typ  
  
1. Definieren Sie eine dynamische Assembly mit der Bezeichnung `GenericEmitExample1`. In diesem Beispiel wird die Assembly ausgeführt und auf einem Datenträger gespeichert, daher wird <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType> angegeben.  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2. Definieren Sie ein dynamisches Modul. Eine Assembly besteht aus ausführbaren Modulen. Der Modulname für eine Assembly mit nur einem Modul ist der gleiche wie der Assemblyname, und der Dateiname ist der Modulname plus eine Erweiterung.  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3. Definieren Sie eine Klasse. In diesem Beispiel heißt die Klasse `Sample`.  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4. Definieren Sie die generischen Typparameter von `Sample`, indem Sie ein Array von Zeichenfolgen, das die Namen der Parameter enthält, an die <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>-Methode übergeben. Dadurch wird die Klasse zu einem generischen Typ. Der Rückgabewert ist ein Array von <xref:System.Reflection.Emit.GenericTypeParameterBuilder>-Objekten, die Typparameter darstellen, die Sie in Ihrem ausgegebenen Code verwenden können.  
  
     Im folgenden Code wird `Sample` zu einem generischen Typ mit den beiden Typparametern `TFirst` und `TSecond` gemacht. Damit der Code einfacher zu lesen ist, wird jede <xref:System.Reflection.Emit.GenericTypeParameterBuilder> in einer Variable mit dem gleichen Namen wie dem des Typparameters platziert.  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5. Fügen Sie den Typparametern besondere Einschränkungen hinzu. In diesem Beispiel wird der Typparameter `TFirst` auf Verweistypen sowie auf Typen beschränkt, die parameterlose Konstruktoren besitzen.  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6. Fügen Sie den Typparametern bei Bedarf Klassen- und Schnittstelleneinschränkungen hinzu. In diesem Beispiel wird der Typparameter `TFirst` auf Typen beschränkt, die von der Basisklasse abgeleitet wurden, die vom in der Variable `baseType` enthaltenen <xref:System.Type>-Objekt dargestellt wird. Diese implementiert die Schnittstellen, dessen Typen in den Variablen `interfaceA` und `interfaceB` enthalten sind. Das Codebeispiel enthält die Deklaration und die Zuweisung dieser Variablen.  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7. Definieren Sie ein Feld. In diesem Beispiel wird der Typ des Felds durch den Typparameter `TFirst` angegeben. <xref:System.Reflection.Emit.GenericTypeParameterBuilder> wird von <xref:System.Type> abgeleitet; Sie können also generische Typparameter immer dort benutzen, wo ein Typ verwendet werden kann.  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8. Definieren Sie eine Methode, die die Typparameter des generischen Typs verwendet. Beachten Sie, dass solche Methoden nicht generisch sind, es sei denn, sie weisen ihre eigenen Typparameterlisten auf. Der folgende Code definiert eine `static`-Methode (`Shared` in Visual Basic), die ein Array von `TFirst` akzeptiert und eine `List<TFirst>` (`List(Of TFirst)` in Visual Basic) zurückgibt, die alle Elemente des Arrays enthält. Um diese Methode zu definieren ist es erforderlich, den Typ `List<TFirst>` zu definieren, indem Sie <xref:System.Type.MakeGenericType%2A> auf der generischen Typdefinition `List<T>` aufrufen. (Die `T` wird ausgelassen, wenn Sie den `typeof`-Operator (`GetType` in Visual Basic) verwenden, um die generische Typdefinition zu erhalten.) Der Parametertyp wird mithilfe der <xref:System.Type.MakeArrayType%2A>-Methode erstellt.  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. Geben Sie den Methodentext aus. Der Methodentext enthält drei Opcodes, die das Eingabearray auf den Stapel laden, den `List<TFirst>`-Konstruktor aufrufen und zurückgeben, der `IEnumerable<TFirst>` nimmt (was die Eingabeelemente in die Liste lädt), wobei das neue <xref:System.Collections.Generic.List%601>-Objekt auf dem Stapel gelassen wird. Der schwierige Teil beim Ausgeben dieses Codes ist es, den Konstruktor abzurufen.  
  
     Die <xref:System.Type.GetConstructor%2A>-Methode wird auf einer <xref:System.Reflection.Emit.GenericTypeParameterBuilder> nicht unterstützt, also ist es nicht möglich, den Konstruktor von `List<TFirst>` direkt zu erhalten. Zunächst ist es erforderlich, den Konstruktor der generischen Typdefinition `List<T>` abzurufen und dann eine Methode aufzurufen, die ihn in den entsprechenden Konstruktor von `List<TFirst>` konvertiert.  
  
     Der Konstruktor, der für dieses Codebeispiel verwendet wird, nimmt eine `IEnumerable<T>`. Beachten Sie, dass dies jedoch nicht die generische Typdefinition der generischen Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> ist. Der Typparameter `T` von `List<T>` muss stattdessen mit dem Typparameter `T` von `IEnumerable<T>` ersetzt werden. (Das klingt zunächst etwas kompliziert, da beide Typen über die Typparameter mit dem Namen `T` verfügen. Darum verwendet dieses Codebeispiel die Namen `TFirst` und `TSecond`.) Um den Typ des Konstruktorarguments zu erhalten, beginnen Sie mit der generischen Typdefinition `IEnumerable<T>`, und rufen Sie <xref:System.Type.MakeGenericType%2A> mit dem ersten generischen Typparameter von `List<T>` ab. Die Liste des Konstruktorarguments muss als Array übergeben werden, wobei in diesem Fall nur ein Argument vorhanden ist.  
  
    > [!NOTE]
    > Die generische Typdefinition wird als `IEnumerable<>` ausgedrückt, wenn Sie den `typeof`-Operator in C# verwenden. Alternativ als `IEnumerable(Of )`, wenn Sie den `GetType`-Operator in Visual Basic verwenden.  
  
     Es ist nun möglich, den Konstruktor von `List<T>` abzurufen, indem Sie <xref:System.Type.GetConstructor%2A> auf der generischen Typdefinition aufrufen. Um diesen Konstruktor in den entsprechenden Konstruktor von `List<TFirst>` zu konvertieren, übergeben Sie `List<TFirst>` und den Konstruktor von `List<T>` an die statische <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=nameWithType>-Methode.  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. Erstellen Sie den Typ, und Speichern Sie die Datei.  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. Rufen Sie die Methode auf. `ExampleMethod` ist nicht generisch, jedoch ist der zugehörige Typ generisch. Um also eine <xref:System.Reflection.MethodInfo> zu erhalten, die aufgerufen werden kann, ist es erforderlich, einen erstellten Typ aus der Typdefinition von `Sample` zu erstellen. Der konstruierte Typ verwendet die `Example`-Klasse, die die Einschränkungen für `TFirst` erfüllt, da es sich hierbei um einen Verweistyp handelt und dieser über einen parameterlosen Standardkonstruktor verfügt, sowie die `ExampleDerived`-Klasse, die die Einschränkungen für `TSecond` erfüllt. (Den Code für `ExampleDerived` finden Sie im Beispielcodeabschnitt.) Diese beiden Typen werden an <xref:System.Type.MakeGenericType%2A> übergeben, um den konstruierten Typ zu erstellen. Die <xref:System.Reflection.MethodInfo> wird dann mithilfe der <xref:System.Type.GetMethod%2A>-Methode abgerufen.  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. Der folgende Code erstellt ein Array von `Example`-Objekten, platziert dieses Array in einem Array des Typs <xref:System.Object>, der die Argumente der aufzurufenden Methode darstellt, und übergibt sie an die <xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29>-Methode. Das erste Argument der <xref:System.Reflection.MethodBase.Invoke%2A>-Methode ist ein NULL-Verweis, da die Methode `static` ist.  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert eine Klasse namens `Sample`, zusammen mit einer Basisklasse und zwei Schnittstellen. Das Programm definiert zwei generische Typparameter für `Sample` und wandelt sie in einen generischen Typ um. Typparameter sind das Einzige, das einen Typ generisch macht. Das Programm stellt dies dar, indem eine Testnachricht vor und nach der Definition der Typparameter angezeigt wird.  
  
 Der Typparameter `TSecond` wird auch zur Darstellung von Klassen- und Schnittstelleneinschränkungen verwendet. Hierzu wird die Basisklasse und die Schnittstellen verwendet, und der Typparameter `TFirst` wird zur Darstellung besonderer Einschränkungen verwendet.  
  
 Das Codebeispiel definiert ein Feld und eine Methode, indem die Typparameter der Klasse für den Feldtyp und für den Parameter sowie den Rückgabetyp der Methode verwendet wird.  
  
 Nachdem die `Sample`-Klasse erstellt wurde, wird die Methode aufgerufen.  
  
 Das Programm enthält eine Methode, die Informationen über einen generischen Typ auflistet, sowie eine Methode, die die besonderen Einschränkungen für einen Typparameter auflistet. Diese Methoden werden zur Darstellung von Informationen über die abgeschlossene `Sample`-Klasse verwendet.  
  
 Das Programm speichert die abgeschlossenen Module als `GenericEmitExample1.dll` auf dem Datenträger, damit Sie sie mit dem [Ildasm.exe (IL-Disassembler)](../tools/ildasm-exe-il-disassembler.md) öffnen können und die MSIL für die `Sample`-Klasse untersuchen können.  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.Emit.GenericTypeParameterBuilder>
- [Verwenden der Reflektionsausgabe](/previous-versions/dotnet/netframework-4.0/3y322t50(v=vs.100))
- [Szenarios für die Reflektionsausgabe mit dynamischen Assemblys](/previous-versions/dotnet/netframework-4.0/tt9483fk(v=vs.100))

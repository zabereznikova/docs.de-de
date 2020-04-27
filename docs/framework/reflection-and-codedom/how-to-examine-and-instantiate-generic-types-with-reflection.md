---
title: 'Vorgehensweise: Untersuchen und Instanziieren von generischen Typen mit Reflektion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
ms.openlocfilehash: 62e4e066740d0422f8f7045b043a5725278c209c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130134"
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a>Vorgehensweise: Untersuchen und Instanziieren von generischen Typen mit Reflektion
Informationen zu generischen Typen können Sie genauso abrufen wie Informationen zu anderen Typen: indem Sie sich ein <xref:System.Type>-Objekt anschauen, das den generischen Typ darstellt. Der größte Unterschied besteht dabei darin, dass eine generischer Type eine Liste von <xref:System.Type>-Objekten hat, die dessen generischen Typparameter darstellen. Die erste Prozedur in diesem Abschnitt beschäftigt sich mit generischen Typen.  
  
 Sie können ein <xref:System.Type>-Objekt erstellen, dass einen konstruierten Typ darstellt, indem Sie Typargumente an die Typparameter einer generischen Typdefinition binden. Dies wird in der zweiten Prozedur veranschaulicht.  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a>So können Sie einen generischen Typ und dessen Typparameter untersuchen  
  
1. Rufen Sie eine Instanz von <xref:System.Type> ab, die den generischen Typ darstellt. Im folgenden Code wird der Typ mit dem `typeof`-Operator von C# abgerufen (`GetType` in Visual Basic, `typeid` in Visual C++). Informationen zu anderen Möglichkeiten zum Abrufen eines <xref:System.Type>-Objekts finden Sie im Thema zur <xref:System.Type>-Klasse. Beachten Sie, dass der Typ für den Rest der Prozedur im Methodenparameter `t` enthalten ist.  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2. Verwenden Sie die <xref:System.Type.IsGenericType%2A>-Eigenschaft, um zu bestimmen, ob der Typ generisch ist. Verwenden Sie die <xref:System.Type.IsGenericTypeDefinition%2A>-Eigenschaft, um zu bestimmen, ob der Typ eine generische Typdefinition ist.  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3. Rufen Sie ein Array mit der <xref:System.Type.GetGenericArguments%2A>-Methode ab, das die generischen Typargumente enthält.  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4. Bestimmen Sie mit der <xref:System.Type.IsGenericParameter%2A>-Methode für jedes Typargument, ob es sich dabei um einen Typparameter handelt (z.B. in einer generischen Typdefinition) oder um einen Typ, der für einen Typparameter angegeben wurde (z.B. in einem konstruierten Typ).  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5. Ein generischer Typparameter wird im Typsystem von einer Instanz von <xref:System.Type> dargestellt, genauso wie normale Typen. In folgendem Code wird der Name und die Parameterposition eines <xref:System.Type>-Objekts gezeigt, das einen generischen Typparameter darstellt. Die Parameterposition ist an dieser Stelle eine unwichtige Information. Sie ist bei der Untersuchung eines Typparameters wichtig, der als Typargument eines anderen generischen Typs verwendet wurde.  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6. Bestimmen Sie mit der <xref:System.Type.GetGenericParameterConstraints%2A>-Methode die Einschränkung des Basistyps und die Schnittstelleneinschränkungen eines generischen Typparameters, um alle Einschränkungen eines einzelnen Arrays zu erhalten. Es ist nicht gewährleistet, dass die Einschränkungen in einer bestimmten Reihenfolge angezeigt werden.  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7. Verwenden Sie die <xref:System.Type.GenericParameterAttributes%2A>-Eigenschaft, um die spezielle Einschränkungen eines Typparameters zu erfahren, z.B. die Anforderung, dass es sich dabei um einen Verweistyp handeln muss. Die Eigenschaft enthält außerdem Werte, die Varianz darstellen. Diese können Sie, wie in folgendem Code gezeigt, abtrennen.  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8. Die Attribute der speziellen Einschränkung sind Flags. Das gleiche Flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>), das keine speziellen Einschränkungen darstellt, steht ebenso für keine Kovarianz oder Kontravarianz. Deshalb müssen Sie für jede dieser Bedingungen die entsprechende Maske verwenden. Verwenden Sie in diesem Fall <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType>, um das Flag für die spezielle Einschränkung zu isolieren.  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a>Konstruieren einer Instanz eines generischen Typs  
 Ein generischer Typ ähnelt einer Vorlage. Sie können nur dann Instanzen des Typs erstellen, wenn Sie die echten Typen seiner generischen Typparameter angeben. Wenn Sie dies zur Runtime mit Reflektion machen möchten, ist die <xref:System.Type.MakeGenericType%2A>-Methode erforderlich.  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a>So konstruieren Sie eine Instanz eines generischen Typs  
  
1. Rufen Sie ein <xref:System.Type>-Objekt ab, das den generischen Typ darstellt. Der folgende Code rufe den generischen Typ <xref:System.Collections.Generic.Dictionary%602> auf zwei verschiedene Weisen ab: Entweder mit der <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType>-Methodenüberladung mit einer Zeichenfolge, die den Typ beschreibt, oder durch Aufrufen der <xref:System.Type.GetGenericTypeDefinition%2A>-Methode auf dem konstruierten Typ `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic). Die <xref:System.Type.MakeGenericType%2A>-Methode erfordert eine generische Typdefinition.  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2. Konstruieren Sie ein Array aus Typargumenten, um die Typparameter zu ersetzen. Das Array muss die richtige Zahl an <xref:System.Type>-Objekten enthalten, und zwar in der gleichen Reihenfolge wie Sie in der Liste der Typparameter auftauchen. In diesem Fall ist der Schlüssel (der erste Typparameter) vom Typ <xref:System.String>, und die Werte im Wörterbuch sind Instanzen der Klasse `Example`.  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3. Rufen Sie die <xref:System.Type.MakeGenericType%2A>-Methode auf, um Typargumente an die Typparameter zu binden, und konstruieren Sie den Typ.  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4. Verwenden Sie die <xref:System.Activator.CreateInstance%28System.Type%29>-Methodenüberladung, um ein Objekt des konstruierten Typs zu erstellen. Der folgende Code speichert zwei Instanzen der `Example`-Klasse im resultierenden `Dictionary<String, Example>`-Objekt.  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a>Beispiel  
 In folgendem Codebeispiel wird eine `DisplayGenericType`-Methode definiert, um die im Code verwendeten generischen Typdefinitionen und konstruierten Typen zu untersuchen und deren Informationen anzuzeigen. Die `DisplayGenericType`-Methode zeigt, wie Sie die Eigenschaften <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> und <xref:System.Type.GenericParameterPosition%2A> und die <xref:System.Type.GetGenericArguments%2A>-Methode verwenden können.  
  
 Im Beispiel wird auch eine `DisplayGenericParameter`-Methode definiert, um einen generischen Typparameter zu untersuchen und dessen Einschränkungen anzuzeigen.  
  
 Im Codebeispiel wird ein Satz von Testtypen definiert, darunter ein generischer Typ, der Typparametereinschränkungen veranschaulicht. Außerdem wird gezeigt, wie Sie Informationen zu diesen Typen anzeigen können.  
  
 Im Beispiel wird ein Typ aus der <xref:System.Collections.Generic.Dictionary%602>-Klasse erstellt, indem ein Array von Typargumenten erstellt und die <xref:System.Type.MakeGenericType%2A>-Methode aufgerufen wird. Das Programm vergleicht das mit <xref:System.Type.MakeGenericType%2A> konstruierte <xref:System.Type>-Objekt mit einem <xref:System.Type>-Objekt, das mit `typeof` (`GetType` in Visual Basic) abgerufen wurde. Es wird gezeigt, dass Sie einander entsprechen. Gleichermaßen verwendet das Programm die <xref:System.Type.GetGenericTypeDefinition%2A>-Methode, um die generische Typdefinition des konstruierten Typs zu erhalten, und vergleicht diese mit dem <xref:System.Type>-Objekt, das die <xref:System.Collections.Generic.Dictionary%602>-Klasse darstellt.  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Type>
- <xref:System.Reflection.MethodInfo>
- [Reflektion und generische Typen](reflection-and-generic-types.md)
- [Anzeigen von Typinformationen](viewing-type-information.md)
- [Generics](../../standard/generics/index.md)

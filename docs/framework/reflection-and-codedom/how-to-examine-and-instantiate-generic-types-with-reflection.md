---
title: 'Gewusst wie: Untersuchen und Instanziieren von generischen Typen mit Reflektion'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5439975adcb6329ef072ef5a2bc98155e56c033
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a><span data-ttu-id="98116-102">Gewusst wie: Untersuchen und Instanziieren von generischen Typen mit Reflektion</span><span class="sxs-lookup"><span data-stu-id="98116-102">How to: Examine and Instantiate Generic Types with Reflection</span></span>
<span data-ttu-id="98116-103">Informationen zu generischen Typen können Sie genauso abrufen wie Informationen zu anderen Typen: indem Sie sich ein <xref:System.Type>-Objekt anschauen, das den generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="98116-103">Information about generic types is obtained in the same way as information about other types: by examining a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="98116-104">Der größte Unterschied besteht dabei darin, dass eine generischer Type eine Liste von <xref:System.Type>-Objekten hat, die dessen generischen Typparameter darstellen.</span><span class="sxs-lookup"><span data-stu-id="98116-104">The principle difference is that a generic type has a list of <xref:System.Type> objects representing its generic type parameters.</span></span> <span data-ttu-id="98116-105">Die erste Prozedur in diesem Abschnitt beschäftigt sich mit generischen Typen.</span><span class="sxs-lookup"><span data-stu-id="98116-105">The first procedure in this section examines generic types.</span></span>  
  
 <span data-ttu-id="98116-106">Sie können ein <xref:System.Type>-Objekt erstellen, dass einen konstruierten Typ darstellt, indem Sie Typargumente an die Typparameter einer generischen Typdefinition binden.</span><span class="sxs-lookup"><span data-stu-id="98116-106">You can create a <xref:System.Type> object that represents a constructed type by binding type arguments to the type parameters of a generic type definition.</span></span> <span data-ttu-id="98116-107">Dies wird in der zweiten Prozedur veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="98116-107">The second procedure demonstrates this.</span></span>  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a><span data-ttu-id="98116-108">So können Sie einen generischen Typ und dessen Typparameter untersuchen</span><span class="sxs-lookup"><span data-stu-id="98116-108">To examine a generic type and its type parameters</span></span>  
  
1.  <span data-ttu-id="98116-109">Rufen Sie eine Instanz von <xref:System.Type> ab, die den generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="98116-109">Get an instance of <xref:System.Type> that represents the generic type.</span></span> <span data-ttu-id="98116-110">Im folgenden Code wird der Typ mit dem `typeof`-Operator von C# abgerufen (`GetType` in Visual Basic, `typeid` in Visual C++).</span><span class="sxs-lookup"><span data-stu-id="98116-110">In the following code, the type is obtained using the C# `typeof` operator (`GetType` in Visual Basic, `typeid` in Visual C++).</span></span> <span data-ttu-id="98116-111">Informationen zu anderen Möglichkeiten zum Abrufen eines <xref:System.Type>-Objekts finden Sie im Thema zur <xref:System.Type>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="98116-111">See the <xref:System.Type> class topic for other ways to get a <xref:System.Type> object.</span></span> <span data-ttu-id="98116-112">Beachten Sie, dass der Typ für den Rest der Prozedur im Methodenparameter `t` enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="98116-112">Note that in the rest of this procedure, the type is contained in a method parameter named `t`.</span></span>  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2.  <span data-ttu-id="98116-113">Verwenden Sie die <xref:System.Type.IsGenericType%2A>-Eigenschaft, um zu bestimmen, ob der Typ generisch ist. Verwenden Sie die <xref:System.Type.IsGenericTypeDefinition%2A>-Eigenschaft, um zu bestimmen, ob der Typ eine generische Typdefinition ist.</span><span class="sxs-lookup"><span data-stu-id="98116-113">Use the <xref:System.Type.IsGenericType%2A> property to determine whether the type is generic, and use the <xref:System.Type.IsGenericTypeDefinition%2A> property to determine whether the type is a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3.  <span data-ttu-id="98116-114">Rufen Sie ein Array mit der <xref:System.Type.GetGenericArguments%2A>-Methode ab, das die generischen Typargumente enthält.</span><span class="sxs-lookup"><span data-stu-id="98116-114">Get an array that contains the generic type arguments, using the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4.  <span data-ttu-id="98116-115">Bestimmen Sie mit der <xref:System.Type.IsGenericParameter%2A>-Methode für jedes Typargument, ob es sich dabei um einen Typparameter handelt (z.B. in einer generischen Typdefinition) oder um einen Typ, der für einen Typparameter angegeben wurde (z.B. in einem konstruierten Typ).</span><span class="sxs-lookup"><span data-stu-id="98116-115">For each type argument, determine whether it is a type parameter (for example, in a generic type definition) or a type that has been specified for a type parameter (for example, in a constructed type), using the <xref:System.Type.IsGenericParameter%2A> property.</span></span>  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5.  <span data-ttu-id="98116-116">Ein generischer Typparameter wird im Typsystem von einer Instanz von <xref:System.Type> dargestellt, genauso wie normale Typen.</span><span class="sxs-lookup"><span data-stu-id="98116-116">In the type system, a generic type parameter is represented by an instance of <xref:System.Type>, just as ordinary types are.</span></span> <span data-ttu-id="98116-117">In folgendem Code wird der Name und die Parameterposition eines <xref:System.Type>-Objekts gezeigt, das einen generischen Typparameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="98116-117">The following code displays the name and parameter position of a <xref:System.Type> object that represents a generic type parameter.</span></span> <span data-ttu-id="98116-118">Die Parameterposition ist an dieser Stelle eine unwichtige Information. Sie ist bei der Untersuchung eines Typparameters wichtig, der als Typargument eines anderen generischen Typs verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="98116-118">The parameter position is trivial information here; it is of more interest when you are examining a type parameter that has been used as a type argument of another generic type.</span></span>  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6.  <span data-ttu-id="98116-119">Bestimmen Sie mit der <xref:System.Type.GetGenericParameterConstraints%2A>-Methode die Einschränkung des Basistyps und die Schnittstelleneinschränkungen eines generischen Typparameters, um alle Einschränkungen eines einzelnen Arrays zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="98116-119">Determine the base type constraint and the interface constraints of a generic type parameter by using the <xref:System.Type.GetGenericParameterConstraints%2A> method to obtain all the constraints in a single array.</span></span> <span data-ttu-id="98116-120">Es ist nicht gewährleistet, dass die Einschränkungen in einer bestimmten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="98116-120">Constraints are not guaranteed to be in any particular order.</span></span>  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7.  <span data-ttu-id="98116-121">Verwenden Sie die <xref:System.Type.GenericParameterAttributes%2A>-Eigenschaft, um die spezielle Einschränkungen eines Typparameters zu erfahren, z.B. die Anforderung, dass es sich dabei um einen Verweistyp handeln muss.</span><span class="sxs-lookup"><span data-stu-id="98116-121">Use the <xref:System.Type.GenericParameterAttributes%2A> property to discover the special constraints on a type parameter, such as requiring that it be a reference type.</span></span> <span data-ttu-id="98116-122">Die Eigenschaft enthält außerdem Werte, die Varianz darstellen. Diese können Sie, wie in folgendem Code gezeigt, abtrennen.</span><span class="sxs-lookup"><span data-stu-id="98116-122">The property also includes values that represent variance, which you can mask off as shown in the following code.</span></span>  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8.  <span data-ttu-id="98116-123">Die Attribute der speziellen Einschränkung sind Flags. Das gleiche Flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>), das keine speziellen Einschränkungen darstellt, steht ebenso für keine Kovarianz oder Kontravarianz.</span><span class="sxs-lookup"><span data-stu-id="98116-123">The special constraint attributes are flags, and the same flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) that represents no special constraints also represents no covariance or contravariance.</span></span> <span data-ttu-id="98116-124">Deshalb müssen Sie für jede dieser Bedingungen die entsprechende Maske verwenden.</span><span class="sxs-lookup"><span data-stu-id="98116-124">Thus, to test for either of these conditions you must use the appropriate mask.</span></span> <span data-ttu-id="98116-125">Verwenden Sie in diesem Fall <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType>, um das Flag für die spezielle Einschränkung zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="98116-125">In this case, use <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> to isolate the special constraint flags.</span></span>  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a><span data-ttu-id="98116-126">Konstruieren einer Instanz eines generischen Typs</span><span class="sxs-lookup"><span data-stu-id="98116-126">Constructing an Instance of a Generic Type</span></span>  
 <span data-ttu-id="98116-127">Ein generischer Typ ähnelt einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="98116-127">A generic type is like a template.</span></span> <span data-ttu-id="98116-128">Sie können nur dann Instanzen des Typs erstellen, wenn Sie die echten Typen seiner generischen Typparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="98116-128">You cannot create instances of it unless you specify real types for its generic type parameters.</span></span> <span data-ttu-id="98116-129">Wenn Sie dies zur Runtime mit Reflektion machen möchten, ist die <xref:System.Type.MakeGenericType%2A>-Methode erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98116-129">To do this at run time, using reflection, requires the <xref:System.Type.MakeGenericType%2A> method.</span></span>  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a><span data-ttu-id="98116-130">So konstruieren Sie eine Instanz eines generischen Typs</span><span class="sxs-lookup"><span data-stu-id="98116-130">To construct an instance of a generic type</span></span>  
  
1.  <span data-ttu-id="98116-131">Rufen Sie ein <xref:System.Type>-Objekt ab, das den generischen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="98116-131">Get a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="98116-132">Der folgende Code rufe den generischen Typ <xref:System.Collections.Generic.Dictionary%602> auf zwei verschiedene Weisen ab: Entweder mit der <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType>-Methodenüberladung mit einer Zeichenfolge, die den Typ beschreibt, oder durch Aufrufen der <xref:System.Type.GetGenericTypeDefinition%2A>-Methode auf dem konstruierten Typ `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="98116-132">The following code gets the generic type <xref:System.Collections.Generic.Dictionary%602> in two different ways: by using the <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> method overload with a string describing the type, and by calling the <xref:System.Type.GetGenericTypeDefinition%2A> method on the constructed type `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic).</span></span> <span data-ttu-id="98116-133">Die <xref:System.Type.MakeGenericType%2A>-Methode erfordert eine generische Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="98116-133">The <xref:System.Type.MakeGenericType%2A> method requires a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2.  <span data-ttu-id="98116-134">Konstruieren Sie ein Array aus Typargumenten, um die Typparameter zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="98116-134">Construct an array of type arguments to substitute for the type parameters.</span></span> <span data-ttu-id="98116-135">Das Array muss die richtige Zahl an <xref:System.Type>-Objekten enthalten, und zwar in der gleichen Reihenfolge wie Sie in der Liste der Typparameter auftauchen.</span><span class="sxs-lookup"><span data-stu-id="98116-135">The array must contain the correct number of <xref:System.Type> objects, in the same order as they appear in the type parameter list.</span></span> <span data-ttu-id="98116-136">In diesem Fall ist der Schlüssel (der erste Typparameter) vom Typ <xref:System.String>, und die Werte im Wörterbuch sind Instanzen der Klasse `Example`.</span><span class="sxs-lookup"><span data-stu-id="98116-136">In this case, the key (first type parameter) is of type <xref:System.String>, and the values in the dictionary are instances of a class named `Example`.</span></span>  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3.  <span data-ttu-id="98116-137">Rufen Sie die <xref:System.Type.MakeGenericType%2A>-Methode auf, um Typargumente an die Typparameter zu binden, und konstruieren Sie den Typ.</span><span class="sxs-lookup"><span data-stu-id="98116-137">Call the <xref:System.Type.MakeGenericType%2A> method to bind the type arguments to the type parameters and construct the type.</span></span>  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4.  <span data-ttu-id="98116-138">Verwenden Sie die <xref:System.Activator.CreateInstance%28System.Type%29>-Methodenüberladung, um ein Objekt des konstruierten Typs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98116-138">Use the <xref:System.Activator.CreateInstance%28System.Type%29> method overload to create an object of the constructed type.</span></span> <span data-ttu-id="98116-139">Der folgende Code speichert zwei Instanzen der `Example`-Klasse im resultierenden `Dictionary<String, Example>`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="98116-139">The following code stores two instances of the `Example` class in the resulting `Dictionary<String, Example>` object.</span></span>  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="98116-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98116-140">Example</span></span>  
 <span data-ttu-id="98116-141">In folgendem Codebeispiel wird eine `DisplayGenericType`-Methode definiert, um die im Code verwendeten generischen Typdefinitionen und konstruierten Typen zu untersuchen und deren Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98116-141">The following code example defines a `DisplayGenericType` method to examine the generic type definitions and constructed types used in the code and display their information.</span></span> <span data-ttu-id="98116-142">Die `DisplayGenericType`-Methode zeigt, wie Sie die Eigenschaften <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> und <xref:System.Type.GenericParameterPosition%2A> und die <xref:System.Type.GetGenericArguments%2A>-Methode verwenden können.</span><span class="sxs-lookup"><span data-stu-id="98116-142">The `DisplayGenericType` method shows how to use the <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A>, and <xref:System.Type.GenericParameterPosition%2A> properties and the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
 <span data-ttu-id="98116-143">Im Beispiel wird auch eine `DisplayGenericParameter`-Methode definiert, um einen generischen Typparameter zu untersuchen und dessen Einschränkungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98116-143">The example also defines a `DisplayGenericParameter` method to examine a generic type parameter and display its constraints.</span></span>  
  
 <span data-ttu-id="98116-144">Im Codebeispiel wird ein Satz von Testtypen definiert, darunter ein generischer Typ, der Typparametereinschränkungen veranschaulicht. Außerdem wird gezeigt, wie Sie Informationen zu diesen Typen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="98116-144">The code example defines a set of test types, including a generic type that illustrates type parameter constraints, and shows how to display information about these types.</span></span>  
  
 <span data-ttu-id="98116-145">Im Beispiel wird ein Typ aus der <xref:System.Collections.Generic.Dictionary%602>-Klasse erstellt, indem ein Array von Typargumenten erstellt und die <xref:System.Type.MakeGenericType%2A>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="98116-145">The example constructs a type from the <xref:System.Collections.Generic.Dictionary%602> class by creating an array of type arguments and calling the <xref:System.Type.MakeGenericType%2A> method.</span></span> <span data-ttu-id="98116-146">Das Programm vergleicht das mit <xref:System.Type.MakeGenericType%2A> konstruierte <xref:System.Type>-Objekt mit einem <xref:System.Type>-Objekt, das mit `typeof` (`GetType` in Visual Basic) abgerufen wurde. Es wird gezeigt, dass Sie einander entsprechen.</span><span class="sxs-lookup"><span data-stu-id="98116-146">The program compares the <xref:System.Type> object constructed using <xref:System.Type.MakeGenericType%2A> with a <xref:System.Type> object obtained using `typeof` (`GetType` in Visual Basic), demonstrating that they are the same.</span></span> <span data-ttu-id="98116-147">Gleichermaßen verwendet das Programm die <xref:System.Type.GetGenericTypeDefinition%2A>-Methode, um die generische Typdefinition des konstruierten Typs zu erhalten, und vergleicht diese mit dem <xref:System.Type>-Objekt, das die <xref:System.Collections.Generic.Dictionary%602>-Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="98116-147">Similarly, the program uses the <xref:System.Type.GetGenericTypeDefinition%2A> method to obtain the generic type definition of the constructed type, and compares it to the <xref:System.Type> object representing the <xref:System.Collections.Generic.Dictionary%602> class.</span></span>  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98116-148">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="98116-148">Compiling the Code</span></span>  
  
-   <span data-ttu-id="98116-149">Der Code enthält die für die Kompilierung erforderlichen `using`-Anweisungen für C# (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="98116-149">The code contains the C# `using` statements (`Imports` in Visual Basic) necessary for compilation.</span></span>  
  
-   <span data-ttu-id="98116-150">Er werden keine weiteren Assemblyverweise benötigt.</span><span class="sxs-lookup"><span data-stu-id="98116-150">No additional assembly references are required.</span></span>  
  
-   <span data-ttu-id="98116-151">Kompilieren Sie den Code über die Befehlszeile mit csc.exe, vbc.exe oder cl.exe.</span><span class="sxs-lookup"><span data-stu-id="98116-151">Compile the code at the command line using csc.exe, vbc.exe, or cl.exe.</span></span> <span data-ttu-id="98116-152">Um den Code in Visual Studio zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="98116-152">To compile the code in Visual Studio, place it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98116-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98116-153">See Also</span></span>  
 <xref:System.Type>  
 <xref:System.Reflection.MethodInfo>  
 [<span data-ttu-id="98116-154">Reflektion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="98116-154">Reflection and Generic Types</span></span>](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)  
 [<span data-ttu-id="98116-155">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="98116-155">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)  
 [<span data-ttu-id="98116-156">Generika</span><span class="sxs-lookup"><span data-stu-id="98116-156">Generics</span></span>](../../../docs/standard/generics/index.md)

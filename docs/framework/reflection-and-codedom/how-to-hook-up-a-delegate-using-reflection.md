---
title: "Gewusst wie: Verknüpfen mit einem Delegaten anhand von Reflektion"
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
- events [.NET Framework], adding event handlers with reflection
- reflection, adding event-handler delegates
- delegates [.NET Framework], adding event handlers with reflection
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ff800eb78b07fc79193c2aa8cb71a461be2fc1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="9ffc7-102">Gewusst wie: Verknüpfen mit einem Delegaten anhand von Reflektion</span><span class="sxs-lookup"><span data-stu-id="9ffc7-102">How to: Hook Up a Delegate Using Reflection</span></span>
<span data-ttu-id="9ffc7-103">Wenn Sie Assemblys mithilfe von Reflektion laden und ausführen, können Sie Ereignisse nicht mit Sprachfunktionen wie dem Operator `+=` von C# oder der [AddHandler-Anweisung](~/docs/visual-basic/language-reference/statements/addhandler-statement.md) von Visual Basic verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-103">When you use reflection to load and run assemblies, you cannot use language features like the C# `+=` operator or the Visual Basic [AddHandler statement](~/docs/visual-basic/language-reference/statements/addhandler-statement.md) to hook up events.</span></span> <span data-ttu-id="9ffc7-104">In den folgenden Verfahrensweisen wird veranschaulicht, wie eine vorhandene Methode mit einem Ereignis verknüpft wird, indem alle erforderlichen Typen über Reflektion abgerufen werden, und wie eine dynamische Methode mithilfe von Reflektionsausgabe erstellt und mit einem Ereignis verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-104">The following procedures show how to hook up an existing method to an event by getting all the necessary types through reflection, and how to create a dynamic method using reflection emit and hook it up to an event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ffc7-105">Eine andere Möglichkeit, einen Delegaten für die Ereignisbehandlung zu verknüpfen, zeigt das Codebeispiel für die <xref:System.Reflection.EventInfo.AddEventHandler%2A>-Methode der <xref:System.Reflection.EventInfo>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-105">For another way to hook up an event-handling delegate, see the code example for the <xref:System.Reflection.EventInfo.AddEventHandler%2A> method of the <xref:System.Reflection.EventInfo> class.</span></span>  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="9ffc7-106">So verknüpfen Sie einen Delegaten mithilfe von Reflektion</span><span class="sxs-lookup"><span data-stu-id="9ffc7-106">To hook up a delegate using reflection</span></span>  
  
1.  <span data-ttu-id="9ffc7-107">Laden Sie eine Assembly, die einen Typ enthält, der Ereignisse auslöst.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-107">Load an assembly that contains a type that raises events.</span></span> <span data-ttu-id="9ffc7-108">Assemblys werden üblicherweise anhand der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode geladen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-108">Assemblies are usually loaded with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9ffc7-109">Um dieses Beispiel möglichst einfach zu halten, wird ein abgeleitetes Formular in der aktuellen Assembly verwendet, es wird daher die <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>-Methode zum Laden der aktuellen Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-109">To keep this example simple, a derived form in the current assembly is used, so the <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method is used to load the current assembly.</span></span>  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2.  <span data-ttu-id="9ffc7-110">Rufen Sie ein <xref:System.Type>-Objekt ab, das den Typ darstellt, und erstellen Sie eine Instanz des Typs.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-110">Get a <xref:System.Type> object representing the type, and create an instance of the type.</span></span> <span data-ttu-id="9ffc7-111">Da das Formular über einen Standardkonstruktor verfügt, wird im folgenden Code die <xref:System.Activator.CreateInstance%28System.Type%29>-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-111">The <xref:System.Activator.CreateInstance%28System.Type%29> method is used in the following code because the form has a default constructor.</span></span> <span data-ttu-id="9ffc7-112">Es gibt verschiedene andere Überladungen der <xref:System.Activator.CreateInstance%2A>-Methode, die Sie verwenden können, wenn der erstellte Typ nicht über einen Standardkonstruktor verfügt.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-112">There are several other overloads of the <xref:System.Activator.CreateInstance%2A> method that you can use if the type you are creating does not have a default constructor.</span></span> <span data-ttu-id="9ffc7-113">Die neue Instanz wird als Typ <xref:System.Object> gespeichert, um bei der Idee zu bleiben, dass keine Informationen über die Assembly bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-113">The new instance is stored as type <xref:System.Object> to maintain the fiction that nothing is known about the assembly.</span></span> <span data-ttu-id="9ffc7-114">(Mithilfe der Reflektion können Sie die Typen in einer Assembly abrufen, ohne ihre Namen bereits zu kennen.)</span><span class="sxs-lookup"><span data-stu-id="9ffc7-114">(Reflection allows you to get the types in an assembly without knowing their names in advance.)</span></span>  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3.  <span data-ttu-id="9ffc7-115">Rufen Sie ein <xref:System.Reflection.EventInfo>-Objekt ab, dass das Ereignis darstellt, und rufen Sie mithilfe der <xref:System.Reflection.EventInfo.EventHandlerType%2A>-Eigenschaft den Typ des Delegaten ab, der für die Ereignisbehandlung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-115">Get an <xref:System.Reflection.EventInfo> object representing the event, and use the <xref:System.Reflection.EventInfo.EventHandlerType%2A> property to get the type of delegate used to handle the event.</span></span> <span data-ttu-id="9ffc7-116">Im folgenden Code wird ein <xref:System.Reflection.EventInfo> für das <xref:System.Windows.Forms.Control.Click>-Ereignis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-116">In the following code, an <xref:System.Reflection.EventInfo> for the <xref:System.Windows.Forms.Control.Click> event is obtained.</span></span>  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4.  <span data-ttu-id="9ffc7-117">Rufen Sie ein <xref:System.Reflection.MethodInfo>-Objekt ab, das die Methode darstellt, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-117">Get a <xref:System.Reflection.MethodInfo> object representing the method that handles the event.</span></span> <span data-ttu-id="9ffc7-118">Der vollständige Programmcode im Thema "Beispiel" weiter unten enthält eine Methode, die der Signatur des <xref:System.EventHandler>-Delegaten entspricht, der das <xref:System.Windows.Forms.Control.Click>-Ereignis behandelt, zur Laufzeit können Sie auch dynamische Methoden generieren.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-118">The complete program code in the Example section later in this topic contains a method that matches the signature of the <xref:System.EventHandler> delegate, which handles the <xref:System.Windows.Forms.Control.Click> event, but you can also generate dynamic methods at run time.</span></span> <span data-ttu-id="9ffc7-119">Einzelheiten finden Sie in der zugehörigen Prozedur zum Generieren eines Ereignishandlers zur Laufzeit durch eine dynamische Methode.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-119">For details, see the accompanying procedure, for generating an event handler at run time by using a dynamic method.</span></span>  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5.  <span data-ttu-id="9ffc7-120">Erstellen Sie mithilfe der <xref:System.Delegate.CreateDelegate%2A>-Methode eine Instanz des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-120">Create an instance of the delegate, using the <xref:System.Delegate.CreateDelegate%2A> method.</span></span> <span data-ttu-id="9ffc7-121">Diese Methode ist statisch (`Shared` in Visual Basic), daher muss der Delegattyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-121">This method is static (`Shared` in Visual Basic), so the delegate type must be supplied.</span></span> <span data-ttu-id="9ffc7-122">Es empfiehlt sich, die Überladungen von <xref:System.Delegate.CreateDelegate%2A> zu verwenden, die eine <xref:System.Reflection.MethodInfo> akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-122">Using the overloads of <xref:System.Delegate.CreateDelegate%2A> that take a <xref:System.Reflection.MethodInfo> is recommended.</span></span>  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6.  <span data-ttu-id="9ffc7-123">Rufen Sie die `add`-Accessormethode ab, und rufen Sie sie auf, auf das Ereignis zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-123">Get the `add` accessor method and invoke it to hook up the event.</span></span> <span data-ttu-id="9ffc7-124">Alle Ereignisse verfügen über einen `add`-Accessor und einen `remove`-Accessor, die durch die Syntax hoch entwickelter Sprachen verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-124">All events have an `add` accessor and a `remove` accessor, which are hidden by the syntax of high-level languages.</span></span> <span data-ttu-id="9ffc7-125">Ereignisse werden beispielsweise in C# mit dem Operator `+=` und in Visual Basic mit der [AddHandler-Anweisung](~/docs/visual-basic/language-reference/statements/addhandler-statement.md) verknüpft.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-125">For example, C# uses the `+=` operator to hook up events, and Visual Basic uses the [AddHandler statement](~/docs/visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="9ffc7-126">Im folgenden Code wird der `add`-Accessor des <xref:System.Windows.Forms.Control.Click>-Ereignisses abgerufen und dieses dann spät gebunden aufgerufen, indem die Delegatinstanz übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-126">The following code gets the `add` accessor of the <xref:System.Windows.Forms.Control.Click> event and invokes it late-bound, passing in the delegate instance.</span></span> <span data-ttu-id="9ffc7-127">Die Argumente müssen als Array übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-127">The arguments must be passed as an array.</span></span>  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7.  <span data-ttu-id="9ffc7-128">Testen Sie das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-128">Test the event.</span></span> <span data-ttu-id="9ffc7-129">Im folgenden Code wird das im Codebeispiel definierte Formular veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-129">The following code shows the form defined in the code example.</span></span> <span data-ttu-id="9ffc7-130">Wenn Sie auf das Formular klicken, wird der Ereignishandler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-130">Clicking the form invokes the event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>   
### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a><span data-ttu-id="9ffc7-131">So generieren Sie anhand einer dynamischen Methode zur Laufzeit einen Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="9ffc7-131">To generate an event handler at run time by using a dynamic method</span></span>  
  
1.  <span data-ttu-id="9ffc7-132">Ereignishandlermethoden können mithilfe einfacher dynamischer Methoden und Reflektionsausgabe zur Laufzeit generiert werden.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-132">Event-handler methods can be generated at run time, using lightweight dynamic methods and reflection emit.</span></span> <span data-ttu-id="9ffc7-133">Zum Erstellen eines Ereignishandlers benötigen Sie den Rückgabetyp und die Parametertypen des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-133">To construct an event handler, you need the return type and parameter types of the delegate.</span></span> <span data-ttu-id="9ffc7-134">Diese können über die `Invoke`-Methode des Delegaten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-134">These can be obtained by examining the delegate's `Invoke` method.</span></span> <span data-ttu-id="9ffc7-135">Im folgenden Code werden diese Informationen über die `GetDelegateReturnType`-Methode und die `GetDelegateParameterTypes`-Methode ermittelt.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-135">The following code uses the `GetDelegateReturnType` and `GetDelegateParameterTypes` methods to obtain this information.</span></span> <span data-ttu-id="9ffc7-136">Den Code für diese Methoden können Sie später in diesem Thema im Abschnitt Beispiel finden.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-136">The code for these methods can be found in the Example section later in this topic.</span></span>  
  
     <span data-ttu-id="9ffc7-137">Eine <xref:System.Reflection.Emit.DynamicMethod> muss nicht bezeichnet werden, Sie können eine leere Zeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-137">It is not necessary to name a <xref:System.Reflection.Emit.DynamicMethod>, so the empty string can be used.</span></span> <span data-ttu-id="9ffc7-138">Im folgenden Code wird die dynamische Methode mit dem letzten Argument dem aktuellen Typ zugeordnet. Dadurch erhält der Delegat Zugriff auf alle öffentlichen und privaten Member der `Example`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-138">In the following code, the last argument associates the dynamic method with the current type, giving the delegate access to all the public and private members of the `Example` class.</span></span>  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2.  <span data-ttu-id="9ffc7-139">Generieren Sie einen Methodentext.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-139">Generate a method body.</span></span> <span data-ttu-id="9ffc7-140">Diese Methode lädt eine Zeichenfolge, ruft die Überladung der <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>-Methode auf, die eine Zeichenfolge akzeptiert, nimmt den Rückgabewert vom Stapel auf (da der Handler keinen Rückgabetyp aufweist) und wird dann beendet.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-140">This method loads a string, calls the overload of the <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> method that takes a string, pops the return value off the stack (because the handler has no return type), and returns.</span></span> <span data-ttu-id="9ffc7-141">Weiter Informationen zum Ausgeben von dynamischen Methoden finden Sie unter [How to: Define and Execute Dynamic Methods (Vorgehensweise: Definieren und Ausführen von dynamischen Methoden)](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="9ffc7-141">To learn more about emitting dynamic methods, see [How to: Define and Execute Dynamic Methods](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md).</span></span>  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3.  <span data-ttu-id="9ffc7-142">Schließen Sie die dynamische Methode ab, indem Sie seine <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-142">Complete the dynamic method by calling its <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="9ffc7-143">Fügen Sie den Delegaten mithilfe des `add`-Accessors zur Aufrufliste des Ereignisses hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-143">Use the `add` accessor to add the delegate to the invocation list for the event.</span></span>  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4.  <span data-ttu-id="9ffc7-144">Testen Sie das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-144">Test the event.</span></span> <span data-ttu-id="9ffc7-145">Im folgenden Code wird das im Codebeispiel definierte Formular geladen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-145">The following code loads the form defined in the code example.</span></span> <span data-ttu-id="9ffc7-146">Wenn Sie auf das Formular klicken, werden sowohl der vordefinierte als auch der ausgegebene Ereignishandler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-146">Clicking the form invokes both the predefined event handler and the emitted event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="9ffc7-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9ffc7-147">Example</span></span>  
 <span data-ttu-id="9ffc7-148">In den folgenden Codebeispielen wird veranschaulicht, wie eine vorhandene Methode anhand von Reflektion mit einem Ereignis verknüpft wird, und wie eine Methode mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse zur Laufzeit ausgegeben und mit einem Ereignis verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-148">The following code example shows how to hook up an existing method to an event using reflection, and also how to use the <xref:System.Reflection.Emit.DynamicMethod> class to emit a method at run time and hook it up to an event.</span></span>  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ffc7-149">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9ffc7-149">Compiling the Code</span></span>  
  
-   <span data-ttu-id="9ffc7-150">Der Code enthält die für die Kompilierung erforderlichen `using`-Anweisungen für C# (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="9ffc7-150">The code contains the C# `using` statements (`Imports` in Visual Basic) necessary for compilation.</span></span>  
  
-   <span data-ttu-id="9ffc7-151">Für die Kompilierung von der Befehlszeile aus sind keine zusätzlichen Assemblyverweise erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-151">No additional assembly references are required for compiling from the command line.</span></span> <span data-ttu-id="9ffc7-152">In Visual Studio müssen Sie einen Verweis auf System.Windows.Forms.dll hinzufügen, da es sich bei diesem Beispiel um eine Konsolenanwendung handelt.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-152">In Visual Studio you must add a reference to System.Windows.Forms.dll because this example is a console application.</span></span>  
  
-   <span data-ttu-id="9ffc7-153">Kompilieren Sie den Code über die Befehlszeile mit csc.exe, vbc.exe oder cl.exe.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-153">Compile the code at the command line using csc.exe, vbc.exe, or cl.exe.</span></span> <span data-ttu-id="9ffc7-154">Um den Code in Visual Studio zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="9ffc7-154">To compile the code in Visual Studio, place it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ffc7-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ffc7-155">See Also</span></span>  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.Emit.DynamicMethod>  
 <xref:System.Activator.CreateInstance%2A>  
 <xref:System.Delegate.CreateDelegate%2A>  
 [<span data-ttu-id="9ffc7-156">Gewusst wie: Definieren und Ausführen von dynamischen Methoden</span><span class="sxs-lookup"><span data-stu-id="9ffc7-156">How to: Define and Execute Dynamic Methods</span></span>](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)  
 [<span data-ttu-id="9ffc7-157">Reflektion</span><span class="sxs-lookup"><span data-stu-id="9ffc7-157">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)

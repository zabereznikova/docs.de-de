---
title: 'Vorgehensweise: Verknüpfen mit einem Delegaten mit Reflektion'
description: So verknüpfen Sie einen Delegaten mit Reflexion in .NET. Verbinden Sie eine vorhandene Methode mit einem Ereignis, indem Sie die erforderlichen Typen über Reflexion erhalten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], adding event handlers with reflection
- reflection, adding event-handler delegates
- delegates [.NET Framework], adding event handlers with reflection
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
ms.openlocfilehash: 9a92afd1c2aeadeb0cf7bc1e626b5bd1fb3cecea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263424"
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="3f7ae-104">Vorgehensweise: Verknüpfen mit einem Delegaten mit Reflektion</span><span class="sxs-lookup"><span data-stu-id="3f7ae-104">How to: Hook Up a Delegate Using Reflection</span></span>

<span data-ttu-id="3f7ae-105">Wenn Sie Assemblys mithilfe von Reflektion laden und ausführen, können Sie Ereignisse nicht mit Sprachfunktionen wie dem Operator `+=` von C# oder der [AddHandler-Anweisung](../../visual-basic/language-reference/statements/addhandler-statement.md) von Visual Basic verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-105">When you use reflection to load and run assemblies, you cannot use language features like the C# `+=` operator or the Visual Basic [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md) to hook up events.</span></span> <span data-ttu-id="3f7ae-106">In den folgenden Verfahrensweisen wird veranschaulicht, wie eine vorhandene Methode mit einem Ereignis verknüpft wird, indem alle erforderlichen Typen über Reflektion abgerufen werden, und wie eine dynamische Methode mithilfe von Reflektionsausgabe erstellt und mit einem Ereignis verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-106">The following procedures show how to hook up an existing method to an event by getting all the necessary types through reflection, and how to create a dynamic method using reflection emit and hook it up to an event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f7ae-107">Eine andere Möglichkeit, einen Delegaten für die Ereignisbehandlung zu verknüpfen, zeigt das Codebeispiel für die <xref:System.Reflection.EventInfo.AddEventHandler%2A>-Methode der <xref:System.Reflection.EventInfo>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-107">For another way to hook up an event-handling delegate, see the code example for the <xref:System.Reflection.EventInfo.AddEventHandler%2A> method of the <xref:System.Reflection.EventInfo> class.</span></span>  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="3f7ae-108">So verknüpfen Sie einen Delegaten mithilfe von Reflektion</span><span class="sxs-lookup"><span data-stu-id="3f7ae-108">To hook up a delegate using reflection</span></span>  
  
1. <span data-ttu-id="3f7ae-109">Laden Sie eine Assembly, die einen Typ enthält, der Ereignisse auslöst.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-109">Load an assembly that contains a type that raises events.</span></span> <span data-ttu-id="3f7ae-110">Assemblys werden üblicherweise anhand der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode geladen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-110">Assemblies are usually loaded with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3f7ae-111">Um dieses Beispiel möglichst einfach zu halten, wird ein abgeleitetes Formular in der aktuellen Assembly verwendet, es wird daher die <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>-Methode zum Laden der aktuellen Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-111">To keep this example simple, a derived form in the current assembly is used, so the <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method is used to load the current assembly.</span></span>  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. <span data-ttu-id="3f7ae-112">Rufen Sie ein <xref:System.Type>-Objekt ab, das den Typ darstellt, und erstellen Sie eine Instanz des Typs.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-112">Get a <xref:System.Type> object representing the type, and create an instance of the type.</span></span> <span data-ttu-id="3f7ae-113">Da das Formular über einen parameterlosen Konstruktor verfügt, wird im folgenden Code die Methode <xref:System.Activator.CreateInstance%28System.Type%29> verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-113">The <xref:System.Activator.CreateInstance%28System.Type%29> method is used in the following code because the form has a parameterless constructor.</span></span> <span data-ttu-id="3f7ae-114">Es gibt verschiedene andere Überladungen der Methode <xref:System.Activator.CreateInstance%2A>, die Sie verwenden können, wenn der erstellte Typ nicht über einen parameterlosen Konstruktor verfügt.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-114">There are several other overloads of the <xref:System.Activator.CreateInstance%2A> method that you can use if the type you are creating does not have a parameterless constructor.</span></span> <span data-ttu-id="3f7ae-115">Die neue Instanz wird als Typ <xref:System.Object> gespeichert, um bei der Idee zu bleiben, dass keine Informationen über die Assembly bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-115">The new instance is stored as type <xref:System.Object> to maintain the fiction that nothing is known about the assembly.</span></span> <span data-ttu-id="3f7ae-116">(Mithilfe der Reflektion können Sie die Typen in einer Assembly abrufen, ohne ihre Namen bereits zu kennen.)</span><span class="sxs-lookup"><span data-stu-id="3f7ae-116">(Reflection allows you to get the types in an assembly without knowing their names in advance.)</span></span>  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. <span data-ttu-id="3f7ae-117">Rufen Sie ein <xref:System.Reflection.EventInfo>-Objekt ab, dass das Ereignis darstellt, und rufen Sie mithilfe der <xref:System.Reflection.EventInfo.EventHandlerType%2A>-Eigenschaft den Typ des Delegaten ab, der für die Ereignisbehandlung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-117">Get an <xref:System.Reflection.EventInfo> object representing the event, and use the <xref:System.Reflection.EventInfo.EventHandlerType%2A> property to get the type of delegate used to handle the event.</span></span> <span data-ttu-id="3f7ae-118">Im folgenden Code wird ein <xref:System.Reflection.EventInfo> für das <xref:System.Windows.Forms.Control.Click>-Ereignis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-118">In the following code, an <xref:System.Reflection.EventInfo> for the <xref:System.Windows.Forms.Control.Click> event is obtained.</span></span>  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. <span data-ttu-id="3f7ae-119">Rufen Sie ein <xref:System.Reflection.MethodInfo>-Objekt ab, das die Methode darstellt, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-119">Get a <xref:System.Reflection.MethodInfo> object representing the method that handles the event.</span></span> <span data-ttu-id="3f7ae-120">Der vollständige Programmcode im Thema "Beispiel" weiter unten enthält eine Methode, die der Signatur des <xref:System.EventHandler>-Delegaten entspricht, der das <xref:System.Windows.Forms.Control.Click>-Ereignis behandelt, zur Laufzeit können Sie auch dynamische Methoden generieren.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-120">The complete program code in the Example section later in this topic contains a method that matches the signature of the <xref:System.EventHandler> delegate, which handles the <xref:System.Windows.Forms.Control.Click> event, but you can also generate dynamic methods at run time.</span></span> <span data-ttu-id="3f7ae-121">Einzelheiten finden Sie in der zugehörigen Prozedur zum Generieren eines Ereignishandlers zur Laufzeit durch eine dynamische Methode.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-121">For details, see the accompanying procedure, for generating an event handler at run time by using a dynamic method.</span></span>  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. <span data-ttu-id="3f7ae-122">Erstellen Sie mithilfe der <xref:System.Delegate.CreateDelegate%2A>-Methode eine Instanz des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-122">Create an instance of the delegate, using the <xref:System.Delegate.CreateDelegate%2A> method.</span></span> <span data-ttu-id="3f7ae-123">Diese Methode ist statisch (`Shared` in Visual Basic), daher muss der Delegattyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-123">This method is static (`Shared` in Visual Basic), so the delegate type must be supplied.</span></span> <span data-ttu-id="3f7ae-124">Es empfiehlt sich, die Überladungen von <xref:System.Delegate.CreateDelegate%2A> zu verwenden, die eine <xref:System.Reflection.MethodInfo> akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-124">Using the overloads of <xref:System.Delegate.CreateDelegate%2A> that take a <xref:System.Reflection.MethodInfo> is recommended.</span></span>  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. <span data-ttu-id="3f7ae-125">Rufen Sie die `add`-Accessormethode ab, und rufen Sie sie auf, auf das Ereignis zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-125">Get the `add` accessor method and invoke it to hook up the event.</span></span> <span data-ttu-id="3f7ae-126">Alle Ereignisse verfügen über einen `add`-Accessor und einen `remove`-Accessor, die durch die Syntax hoch entwickelter Sprachen verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-126">All events have an `add` accessor and a `remove` accessor, which are hidden by the syntax of high-level languages.</span></span> <span data-ttu-id="3f7ae-127">Ereignisse werden beispielsweise in C# mit dem Operator `+=` und in Visual Basic mit der [AddHandler-Anweisung](../../visual-basic/language-reference/statements/addhandler-statement.md) verknüpft.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-127">For example, C# uses the `+=` operator to hook up events, and Visual Basic uses the [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="3f7ae-128">Im folgenden Code wird der `add`-Accessor des <xref:System.Windows.Forms.Control.Click>-Ereignisses abgerufen und dieses dann spät gebunden aufgerufen, indem die Delegatinstanz übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-128">The following code gets the `add` accessor of the <xref:System.Windows.Forms.Control.Click> event and invokes it late-bound, passing in the delegate instance.</span></span> <span data-ttu-id="3f7ae-129">Die Argumente müssen als Array übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-129">The arguments must be passed as an array.</span></span>  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. <span data-ttu-id="3f7ae-130">Testen Sie das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-130">Test the event.</span></span> <span data-ttu-id="3f7ae-131">Im folgenden Code wird das im Codebeispiel definierte Formular veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-131">The following code shows the form defined in the code example.</span></span> <span data-ttu-id="3f7ae-132">Wenn Sie auf das Formular klicken, wird der Ereignishandler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-132">Clicking the form invokes the event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>

### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a><span data-ttu-id="3f7ae-133">So generieren Sie anhand einer dynamischen Methode zur Laufzeit einen Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="3f7ae-133">To generate an event handler at run time by using a dynamic method</span></span>  
  
1. <span data-ttu-id="3f7ae-134">Ereignishandlermethoden können mithilfe einfacher dynamischer Methoden und Reflektionsausgabe zur Laufzeit generiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-134">Event-handler methods can be generated at run time, using lightweight dynamic methods and reflection emit.</span></span> <span data-ttu-id="3f7ae-135">Zum Erstellen eines Ereignishandlers benötigen Sie den Rückgabetyp und die Parametertypen des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-135">To construct an event handler, you need the return type and parameter types of the delegate.</span></span> <span data-ttu-id="3f7ae-136">Diese können über die `Invoke`-Methode des Delegaten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-136">These can be obtained by examining the delegate's `Invoke` method.</span></span> <span data-ttu-id="3f7ae-137">Im folgenden Code werden diese Informationen über die `GetDelegateReturnType`-Methode und die `GetDelegateParameterTypes`-Methode ermittelt.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-137">The following code uses the `GetDelegateReturnType` and `GetDelegateParameterTypes` methods to obtain this information.</span></span> <span data-ttu-id="3f7ae-138">Den Code für diese Methoden können Sie später in diesem Thema im Abschnitt Beispiel finden.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-138">The code for these methods can be found in the Example section later in this topic.</span></span>  
  
     <span data-ttu-id="3f7ae-139">Eine <xref:System.Reflection.Emit.DynamicMethod> muss nicht bezeichnet werden, Sie können eine leere Zeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-139">It is not necessary to name a <xref:System.Reflection.Emit.DynamicMethod>, so the empty string can be used.</span></span> <span data-ttu-id="3f7ae-140">Im folgenden Code wird die dynamische Methode mit dem letzten Argument dem aktuellen Typ zugeordnet. Dadurch erhält der Delegat Zugriff auf alle öffentlichen und privaten Member der `Example`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-140">In the following code, the last argument associates the dynamic method with the current type, giving the delegate access to all the public and private members of the `Example` class.</span></span>  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. <span data-ttu-id="3f7ae-141">Generieren Sie einen Methodentext.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-141">Generate a method body.</span></span> <span data-ttu-id="3f7ae-142">Diese Methode lädt eine Zeichenfolge, ruft die Überladung der <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>-Methode auf, die eine Zeichenfolge akzeptiert, nimmt den Rückgabewert vom Stapel auf (da der Handler keinen Rückgabetyp aufweist) und wird dann beendet.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-142">This method loads a string, calls the overload of the <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> method that takes a string, pops the return value off the stack (because the handler has no return type), and returns.</span></span> <span data-ttu-id="3f7ae-143">Weitere Informationen zum Ausgeben dynamischer Methoden finden Sie unter [Vorgehensweise: Definieren und Ausführen von dynamischen Methoden](how-to-define-and-execute-dynamic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="3f7ae-143">To learn more about emitting dynamic methods, see [How to: Define and Execute Dynamic Methods](how-to-define-and-execute-dynamic-methods.md).</span></span>  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. <span data-ttu-id="3f7ae-144">Schließen Sie die dynamische Methode ab, indem Sie seine <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-144">Complete the dynamic method by calling its <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="3f7ae-145">Fügen Sie den Delegaten mithilfe des `add`-Accessors zur Aufrufliste des Ereignisses hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-145">Use the `add` accessor to add the delegate to the invocation list for the event.</span></span>  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. <span data-ttu-id="3f7ae-146">Testen Sie das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-146">Test the event.</span></span> <span data-ttu-id="3f7ae-147">Im folgenden Code wird das im Codebeispiel definierte Formular geladen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-147">The following code loads the form defined in the code example.</span></span> <span data-ttu-id="3f7ae-148">Wenn Sie auf das Formular klicken, werden sowohl der vordefinierte als auch der ausgegebene Ereignishandler aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-148">Clicking the form invokes both the predefined event handler and the emitted event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="3f7ae-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f7ae-149">Example</span></span>  

 <span data-ttu-id="3f7ae-150">In den folgenden Codebeispielen wird veranschaulicht, wie eine vorhandene Methode anhand von Reflektion mit einem Ereignis verknüpft wird, und wie eine Methode mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse zur Laufzeit ausgegeben und mit einem Ereignis verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="3f7ae-150">The following code example shows how to hook up an existing method to an event using reflection, and also how to use the <xref:System.Reflection.Emit.DynamicMethod> class to emit a method at run time and hook it up to an event.</span></span>  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3f7ae-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f7ae-151">See also</span></span>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [<span data-ttu-id="3f7ae-152">How to: Definieren und Ausführen von dynamischen Methoden</span><span class="sxs-lookup"><span data-stu-id="3f7ae-152">How to: Define and Execute Dynamic Methods</span></span>](how-to-define-and-execute-dynamic-methods.md)
- [<span data-ttu-id="3f7ae-153">Reflexion</span><span class="sxs-lookup"><span data-stu-id="3f7ae-153">Reflection</span></span>](reflection.md)

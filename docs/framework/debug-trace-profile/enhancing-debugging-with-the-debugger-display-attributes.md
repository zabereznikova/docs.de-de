---
title: Verbessern des Debuggens mit den Debuggeranzeigeattributen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
ms.openlocfilehash: ca118bffb045a0e7e3a5084916a0ff8020ebda90
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216490"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a><span data-ttu-id="b8919-102">Verbessern des Debuggens mit den Debuggeranzeigeattributen</span><span class="sxs-lookup"><span data-stu-id="b8919-102">Enhancing Debugging with the Debugger Display Attributes</span></span>

<span data-ttu-id="b8919-103">Debuggeranzeigeattribute ermöglichen es dem Entwickler des Typs, der dessen Laufzeitverhalten angibt und am besten versteht, ebenfalls anzugeben, wie der Typ aussieht, wenn er in einem Debugger angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-103">Debugger display attributes allow the developer of the type, who specifies and best understands the runtime behavior of that type, to also specify what that type will look like when it is displayed in a debugger.</span></span> <span data-ttu-id="b8919-104">Zusätzlich können Debuggeranzeigeattribute, die eine `Target`-Eigenschaft bereitstellen, von den Benutzern auf Assemblyebene angewendet werden, ohne dass diese den Quellcode kennen müssen.</span><span class="sxs-lookup"><span data-stu-id="b8919-104">In addition, debugger display attributes that provide a `Target` property can be applied at the assembly level by users without knowledge of the source code.</span></span> <span data-ttu-id="b8919-105">Das <xref:System.Diagnostics.DebuggerDisplayAttribute>-Attribut steuert die Anzeige eines Typs oder Members in den Variablenfenstern des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="b8919-105">The <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute controls how a type or member is displayed in the debugger variable windows.</span></span> <span data-ttu-id="b8919-106">Das <xref:System.Diagnostics.DebuggerBrowsableAttribute>-Attribut bestimmt, ob und wie ein Feld oder eine Eigenschaft in den Variablenfenstern des Debuggers angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-106">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute determines if and how a field or property is displayed in the debugger variable windows.</span></span> <span data-ttu-id="b8919-107">Das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>-Attribut gibt einen Ersatztyp oder einen Proxy für einen Typ an und ändert die Art, wie dieser Typ in Debuggerfenstern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-107">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute specifies a substitute type, or a proxy, for a type and changes the way the type is displayed in debugger windows.</span></span> <span data-ttu-id="b8919-108">Wenn Sie eine Variable mit einem Proxy oder einem Ersatztyp anzeigen, steht der Proxy für den ursprünglichen Typ im Anzeige Fenster des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="b8919-108">When you view a variable that has a proxy, or substitute type, the proxy stands in for the original type in the debugger display window.</span></span> <span data-ttu-id="b8919-109">Im Debuggervariablenfenster werden nur die öffentlichen Member des Proxytyps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8919-109">The debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="b8919-110">Private Member werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8919-110">Private members are not displayed.</span></span>  
  
## <a name="using-the-debuggerdisplayattribute"></a><span data-ttu-id="b8919-111">Verwenden des DebuggerDisplayAttribute-Konstruktors</span><span class="sxs-lookup"><span data-stu-id="b8919-111">Using the DebuggerDisplayAttribute</span></span>  

<span data-ttu-id="b8919-112">Der <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A>-Konstruktor verfügt über ein einziges Argument: Eine Zeichenfolge, die in der Wertspalte für Instanzen des Typs angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-112">The <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> constructor has a single argument: a string to be displayed in the value column for instances of the type.</span></span> <span data-ttu-id="b8919-113">Diese Zeichenfolge kann geschweifte Klammern ({ und }) enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8919-113">This string can contain braces ({ and }).</span></span> <span data-ttu-id="b8919-114">Der Text innerhalb von Klammern wird als Ausdruck ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="b8919-114">The text within a pair of braces is evaluated as an expression.</span></span> <span data-ttu-id="b8919-115">Beispielsweise verursacht der folgende C#-Code, dass „Count = 4“ angezeigt wird, wenn das Pluszeichen (+) angeklickt wird, um die Debuggeranzeige für eine Instanz von `MyHashtable` anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b8919-115">For example, the following C# code causes "Count = 4" to be displayed when the plus sign (+) is selected to expand the debugger display for an instance of `MyHashtable`.</span></span>  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

<span data-ttu-id="b8919-116">Attribute, die auf Eigenschaften angewendet werden, auf die im Ausdruck verwiesen wird, werden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b8919-116">Attributes applied to properties referenced in the expression are not processed.</span></span> <span data-ttu-id="b8919-117">Für den C#-Compiler ist ein allgemeiner Ausdruck zugelassen, der nur über impliziten Zugriff auf diesen Verweis auf die aktuelle Instanz des Zieltyps verfügt.</span><span class="sxs-lookup"><span data-stu-id="b8919-117">For the C# compiler, a general expression is allowed that has only implicit access to this reference for the current instance of the target type.</span></span> <span data-ttu-id="b8919-118">Der Ausdruck ist begrenzt, er hat keinen Zugriff auf Aliase, lokale Variablen oder Zeiger.</span><span class="sxs-lookup"><span data-stu-id="b8919-118">The expression is limited; there is no access to aliases, locals, or pointers.</span></span> <span data-ttu-id="b8919-119">In C#-Code können Sie einen allgemeinen Ausdruck zwischen den Klammern verwenden, der nur über impliziten Zugriff auf den `this`-Zeiger für die aktuelle Instanz des Zieltyps verfügt.</span><span class="sxs-lookup"><span data-stu-id="b8919-119">In C# code, you can use a general expression between the braces that has implicit access to the `this` pointer for the current instance of the target type only.</span></span>

<span data-ttu-id="b8919-120">Wenn bei einem C#-Objekt beispielsweise `ToString()` überschrieben wurde, ruft der Debugger die Überschreibung auf und zeigt deren Ergebnisse anstelle des standardmäßigen `{<typeName>}.` an. Wenn Sie also `ToString()` überschrieben haben, müssen Sie <xref:System.Diagnostics.DebuggerDisplayAttribute> nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8919-120">For example, if a C# object has an overridden `ToString()`, the debugger will call the override and show its result instead of the standard `{<typeName>}.` Thus, if you have overridden `ToString()`, you do not need to use <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span></span> <span data-ttu-id="b8919-121">Wenn Sie beides verwenden, hat das <xref:System.Diagnostics.DebuggerDisplayAttribute>-Attribut Vorrang gegenüber der `ToString()`-Überschreibung.</span><span class="sxs-lookup"><span data-stu-id="b8919-121">If you use both, the <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute takes precedence over the `ToString()` override.</span></span>

## <a name="using-the-debuggerbrowsableattribute"></a><span data-ttu-id="b8919-122">Verwenden von DebuggerBrowsableAttribute</span><span class="sxs-lookup"><span data-stu-id="b8919-122">Using the DebuggerBrowsableAttribute</span></span>
 <span data-ttu-id="b8919-123">Wenden Sie <xref:System.Diagnostics.DebuggerBrowsableAttribute> auf ein Feld oder eine Eigenschaft an, um anzugeben, wie das Feld oder die Eigenschaft im Debuggerfenster angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8919-123">Apply the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to a field or property to specify how the field or property is to be displayed in the debugger window.</span></span> <span data-ttu-id="b8919-124">Der Konstruktor für dieses Attribut nimmt einen der <xref:System.Diagnostics.DebuggerBrowsableState>-Enumerationswerte an, die einen der folgenden Zustände angeben:</span><span class="sxs-lookup"><span data-stu-id="b8919-124">The constructor for this attribute takes one of the <xref:System.Diagnostics.DebuggerBrowsableState> enumeration values, which specifies one of the following states:</span></span>

- <span data-ttu-id="b8919-125"><xref:System.Diagnostics.DebuggerBrowsableState.Never> gibt an, dass das Element nicht im Datenfenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-125"><xref:System.Diagnostics.DebuggerBrowsableState.Never> indicates that the member is not displayed in the data window.</span></span>  <span data-ttu-id="b8919-126">Verwenden Sie diesen Wert beispielsweise für den <xref:System.Diagnostics.DebuggerBrowsableAttribute> eines Felds, um das Feld aus der Hierarchie zu entfernen. Das Feld wird nicht angezeigt, wenn Sie den einschließenden Typ erweitern, indem Sie auf das Pluszeichen (+) für die Typinstanz klicken.</span><span class="sxs-lookup"><span data-stu-id="b8919-126">For example, using this value for the <xref:System.Diagnostics.DebuggerBrowsableAttribute> on a field removes the field from the hierarchy; the field is not displayed when you expand the enclosing type by clicking the plus sign (+) for the type instance.</span></span>

- <span data-ttu-id="b8919-127"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> gibt an, dass das Element angezeigt, aber nicht standardmäßig erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-127"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indicates that the member is displayed but not expanded by default.</span></span>  <span data-ttu-id="b8919-128">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="b8919-128">This is the default behavior.</span></span>

- <span data-ttu-id="b8919-129"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> gibt an, dass das Element selbst nicht angezeigt wird. Seine enthaltenen Objekte werden jedoch angezeigt, wenn es sich bei diesen um Arrays oder Sammlungen handelt.</span><span class="sxs-lookup"><span data-stu-id="b8919-129"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indicates that the member itself is not shown, but its constituent objects are displayed if it is an array or collection.</span></span>

> [!NOTE]
> <span data-ttu-id="b8919-130"><xref:System.Diagnostics.DebuggerBrowsableAttribute> wird von Visual Basic in .NET Framework-Version 2.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b8919-130">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> is not supported by Visual Basic in the .NET Framework version 2.0.</span></span>

<span data-ttu-id="b8919-131">Das folgende Codebeispiel veranschaulicht die Verwendung von <xref:System.Diagnostics.DebuggerBrowsableAttribute>, um zu verhindern, dass die ihm folgende Eigenschaft im Debugfenster für die Klasse angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-131">The following code example shows the use of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to prevent the property following it from appearing in the debug window for the class.</span></span>

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a><span data-ttu-id="b8919-132">Verwenden von DebuggerTypeProxy</span><span class="sxs-lookup"><span data-stu-id="b8919-132">Using the DebuggerTypeProxy</span></span>
 <span data-ttu-id="b8919-133">Verwenden Sie das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>-Attribut, wenn Sie die Debuggingansicht eines Typs erheblich und grundlegend ändern müssen, ohne den Typ selbst zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b8919-133">Use the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute when you need to significantly and fundamentally change the debugging view of a type, but not change the type itself.</span></span> <span data-ttu-id="b8919-134">Das <xref:System.Diagnostics.DebuggerTypeProxyAttribute>-Attribut wird verwendet, um einen Anzeigeproxy für einen Typ anzugeben. Dadurch wird es einem Entwickler ermöglicht, die Ansicht des Typs anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b8919-134">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute is used to specify a display proxy for a type, allowing a developer to tailor the view for the type.</span></span>  <span data-ttu-id="b8919-135">Dieses Attribut kann genau wie <xref:System.Diagnostics.DebuggerDisplayAttribute> auf Assemblyebene verwendet werden. In diesem Fall gibt die <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A>-Eigenschaft den Typ an, für den der Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-135">This attribute, like the <xref:System.Diagnostics.DebuggerDisplayAttribute>, can be used at the assembly level, in which case the <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> property specifies the type for which the proxy will be used.</span></span> <span data-ttu-id="b8919-136">Es wird empfohlen, dass das Attribut einen privaten geschachtelten Typ angibt, der innerhalb des Typs auftritt, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-136">The recommended usage is that this attribute specifies a private nested type that occurs within the type to which the attribute is applied.</span></span>  <span data-ttu-id="b8919-137">Eine Ausdrucksauswertung, die Überprüfungen für die Ansichten von Typen für dieses Attribut unterstützt, wenn ein Typ angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-137">An expression evaluator that supports type viewers checks for this attribute when a type is displayed.</span></span> <span data-ttu-id="b8919-138">Wenn das Attribut gefunden wird, ersetzt die Ausdrucksauswertung den Anzeigeproxytyp für den Typ, auf den das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8919-138">If the attribute is found, the expression evaluator substitutes the display proxy type for the type the attribute is applied to.</span></span>

 <span data-ttu-id="b8919-139">Wenn <xref:System.Diagnostics.DebuggerTypeProxyAttribute> vorhanden ist, werden im Debuggervariablenfenster nur die öffentlichen Member des Proxytyps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8919-139">When the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> is present, the debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="b8919-140">Private Member werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8919-140">Private members are not displayed.</span></span> <span data-ttu-id="b8919-141">Das Verhalten des Datenfensters wird durch von Attributen erweiterte Ansichten nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="b8919-141">The behavior of the data window is not changed by attribute-enhanced views.</span></span>

 <span data-ttu-id="b8919-142">Um unnötige Leistungseinbußen zu vermeiden, werden Attribute des Anzeigeproxys nicht verarbeitet, bis das Objekt erweitert wurde. Dies geschieht entweder, indem der Benutzer auf das Pluszeichen (+) neben dem Typ im Datenfenster klickt, oder durch Anwenden des <xref:System.Diagnostics.DebuggerBrowsableAttribute>-Attributs.</span><span class="sxs-lookup"><span data-stu-id="b8919-142">To avoid unnecessary performance penalties, attributes of the display proxy are not processed until the object is expanded, either through the user clicking the plus sign (+) next to the type in a data window, or through the application of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute.</span></span> <span data-ttu-id="b8919-143">Aus diesem Grund wird empfohlen, keine Attribute auf den Anzeigetyp anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b8919-143">Therefore, it is recommended that no attributes be applied to the display type.</span></span> <span data-ttu-id="b8919-144">Attribute können und sollen im Text des Anzeigetyps angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8919-144">Attributes can and should be applied within the body of the display type.</span></span>

 <span data-ttu-id="b8919-145">Das folgende Codebeispiel veranschaulicht die Verwendung von <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, um einen Typ anzugeben, der als Debuggeranzeigeproxy verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8919-145">The following code example shows the use of the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> to specify a type to be used as a debugger display proxy.</span></span>

```csharp
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable : Hashtable
{
    private const string TestString =
        "This should not appear in the debug window.";

    internal class HashtableDebugView
    {
        private Hashtable hashtable;
        public const string TestStringProxy =
            "This should appear in the debug window.";

        // The constructor for the type proxy class must have a
        // constructor that takes the target type as a parameter.
        public HashtableDebugView(Hashtable hashtable)
        {
            this.hashtable = hashtable;
        }
    }
}
```

## <a name="example"></a><span data-ttu-id="b8919-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8919-146">Example</span></span>

### <a name="description"></a><span data-ttu-id="b8919-147">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b8919-147">Description</span></span>

<span data-ttu-id="b8919-148">Das folgende Codebeispiel kann in Visual Studio angezeigt werden, um die Ergebnisse der Anwendung der Attribute "<xref:System.Diagnostics.DebuggerDisplayAttribute>", "<xref:System.Diagnostics.DebuggerBrowsableAttribute>" und "<xref:System.Diagnostics.DebuggerTypeProxyAttribute>" anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b8919-148">The following code example can be viewed in Visual Studio to see the results of applying the <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute>, and <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attributes.</span></span>

### <a name="code"></a><span data-ttu-id="b8919-149">Code</span><span class="sxs-lookup"><span data-stu-id="b8919-149">Code</span></span>

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="b8919-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8919-150">See also</span></span>

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>

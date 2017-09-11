---
title: Enum-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Enum
dev_langs:
- VB
helpviewer_keywords:
- enumerated constants
- Enum statement
- Private keyword, Enum statements
- Public keyword, in Enum statement
- variables [Visual Basic], enumeration
- constants, enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ff075349756bd4c568833d049b50b3c3721d1b08
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="9b713-102">Enum-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b713-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="9b713-103">Deklariert eine Enumeration und definiert die Werte ihrer Member.</span><span class="sxs-lookup"><span data-stu-id="9b713-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b713-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b713-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="9b713-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9b713-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="9b713-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b713-106">Optional.</span></span> <span data-ttu-id="9b713-107">Liste der Attribute, die auf diese Enumeration anwenden.</span><span class="sxs-lookup"><span data-stu-id="9b713-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="9b713-108">Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").</span><span class="sxs-lookup"><span data-stu-id="9b713-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="9b713-109">Die <xref:System.FlagsAttribute>Attribut gibt an, dass der Wert einer Instanz der Enumeration kann mehrere Enumerationsmember und jedes Element ein Bitfeld im Enumerationswert darstellt.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9b713-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="9b713-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b713-110">Optional.</span></span> <span data-ttu-id="9b713-111">Gibt an, welcher Code auf diese Enumeration zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9b713-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="9b713-112">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="9b713-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="9b713-113">Public</span><span class="sxs-lookup"><span data-stu-id="9b713-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="9b713-114">Protected</span><span class="sxs-lookup"><span data-stu-id="9b713-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="9b713-115">Friend</span><span class="sxs-lookup"><span data-stu-id="9b713-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="9b713-116">Private</span><span class="sxs-lookup"><span data-stu-id="9b713-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="9b713-117">Sie können angeben, `Protected``Friend` um Zugriff von Code innerhalb der Enumeration-Klasse, einer abgeleiteten Klasse oder der gleichen Assembly zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="9b713-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="9b713-118">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b713-118">Optional.</span></span> <span data-ttu-id="9b713-119">Gibt an, dass diese Enumeration erneut deklariert und ein Programmierelement mit derselben Bezeichnung oder eine Gruppe überladener Elemente in einer Basisklasse ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="9b713-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="9b713-120">Sie können angeben, [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md) nur für die Enumeration selbst, nicht für einen Member.</span><span class="sxs-lookup"><span data-stu-id="9b713-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="9b713-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b713-121">Required.</span></span> <span data-ttu-id="9b713-122">Der Name der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9b713-122">Name of the enumeration.</span></span> <span data-ttu-id="9b713-123">Informationen zu gültigen Namen finden Sie unter [Elementnamen deklariert](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9b713-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="9b713-124">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b713-124">Optional.</span></span> <span data-ttu-id="9b713-125">Der Datentyp der Enumeration und allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="9b713-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="9b713-126">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b713-126">Required.</span></span> <span data-ttu-id="9b713-127">Liste der Memberkonstanten, die in dieser Anweisung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="9b713-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="9b713-128">Auf einzelnen Quellcodezeilen werden mehrere Member aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9b713-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="9b713-129">Jede `member` hat die folgende Syntax und Bestandteile:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="9b713-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="9b713-130">Segment</span><span class="sxs-lookup"><span data-stu-id="9b713-130">Part</span></span>|<span data-ttu-id="9b713-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b713-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="9b713-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b713-132">Required.</span></span> <span data-ttu-id="9b713-133">Der Name dieses Members.</span><span class="sxs-lookup"><span data-stu-id="9b713-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="9b713-134">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b713-134">Optional.</span></span> <span data-ttu-id="9b713-135">Ein Ausdruck, der zur Kompilierzeit ausgewertet und diesem Member zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9b713-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="9b713-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="9b713-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="9b713-137">Beendet den `Enum`-Block.</span><span class="sxs-lookup"><span data-stu-id="9b713-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b713-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b713-138">Remarks</span></span>  
 <span data-ttu-id="9b713-139">Wenn Sie eine Gruppe unveränderlicher Werte, die logisch miteinander verknüpft sind haben, können Sie diese zusammen in einer Enumeration definieren.</span><span class="sxs-lookup"><span data-stu-id="9b713-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="9b713-140">Dadurch werden aussagekräftige Namen für die Enumeration und seine Member, die leichter merken als die Werte sind.</span><span class="sxs-lookup"><span data-stu-id="9b713-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="9b713-141">Sie können dann die Enumerationsmember an vielen Stellen in Ihrem Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b713-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="9b713-142">Die Vorteile der Verwendung von Enumerationen sind unter anderem:</span><span class="sxs-lookup"><span data-stu-id="9b713-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="9b713-143">Fehler aufgrund eines vertauschen oder falsch eingegebene Zahlen wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="9b713-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="9b713-144">Erleichtert die Werte in der Zukunft ändern.</span><span class="sxs-lookup"><span data-stu-id="9b713-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="9b713-145">Ist der Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9b713-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="9b713-146">Sicherstellung der Vorwärtskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="9b713-146">Ensures forward compatibility.</span></span> <span data-ttu-id="9b713-147">Wenn Sie Enumerationen verwenden, ist der Code weniger wahrscheinlich fehlschlägt, wenn jemand die Namen der entsprechenden Werte ändert.</span><span class="sxs-lookup"><span data-stu-id="9b713-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="9b713-148">Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und eine Menge von Elementen.</span><span class="sxs-lookup"><span data-stu-id="9b713-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="9b713-149">Jedes Element stellt eine Konstante dar.</span><span class="sxs-lookup"><span data-stu-id="9b713-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="9b713-150">Eine Enumeration, die auf die Klasse, Struktur, Modul oder Schnittstellenebene außerhalb einer Prozedur deklariert ist ein *Element Enumeration*.</span><span class="sxs-lookup"><span data-stu-id="9b713-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="9b713-151">Es ist ein Mitglied der Klasse, Struktur, Modul oder Schnittstelle, die es deklariert.</span><span class="sxs-lookup"><span data-stu-id="9b713-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="9b713-152">Enumerationen für Namespacemember können von überall in ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9b713-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="9b713-153">Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss ein der Memberenumeration den Namen mit dem Namen der Klasse, der Struktur oder des Moduls qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="9b713-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="9b713-154">Sie können vermeiden, dass durch Hinzufügen von vollqualifizierte Namen verwenden ein [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Anweisung in der Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="9b713-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="9b713-155">Eine Enumeration, die auf Namespaceebene außerhalb jeder Klasse, Struktur, Modul oder Schnittstelle deklariert ist, ein Mitglied der Namespace, in dem es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9b713-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="9b713-156">Die *Deklarationskontext* für eine Enumeration eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle sein muss und keine Prozedur sein kann.</span><span class="sxs-lookup"><span data-stu-id="9b713-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="9b713-157">Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9b713-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="9b713-158">Sie können Attribute auf die Enumeration als Ganzes, jedoch nicht auf ihre Member einzeln anwenden.</span><span class="sxs-lookup"><span data-stu-id="9b713-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="9b713-159">Ein Attribut fügt die Informationen in den Metadaten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="9b713-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="9b713-160">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9b713-160">Data Type</span></span>  
 <span data-ttu-id="9b713-161">Die `Enum` -Anweisung kann den Datentyp einer Enumeration deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9b713-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="9b713-162">Jedes Element hat den Enumerationstyp Daten.</span><span class="sxs-lookup"><span data-stu-id="9b713-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="9b713-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span><span class="sxs-lookup"><span data-stu-id="9b713-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="9b713-164">Wenn Sie keinen angeben `datatype` für die Enumeration übernimmt jeder Member den Datentyp der `initializer`.</span><span class="sxs-lookup"><span data-stu-id="9b713-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="9b713-165">Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` muss in konvertierbar sein `datatype`.</span><span class="sxs-lookup"><span data-stu-id="9b713-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="9b713-166">Wenn weder `datatype` noch `initializer` vorhanden ist, der Datentyp, der Standardwert ist `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9b713-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="9b713-167">Initialisieren von Membern</span><span class="sxs-lookup"><span data-stu-id="9b713-167">Initializing Members</span></span>  
 <span data-ttu-id="9b713-168">Die `Enum` -Anweisung kann den Inhalt der ausgewählten Elemente in initialisieren `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="9b713-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="9b713-169">Verwenden Sie `initializer` , geben Sie einen Ausdruck, der das Element zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b713-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="9b713-170">Wenn Sie keinen angeben `initializer` für ein Mitglied initialisiert Visual Basic diesen entweder&0; (null) (ist dies die erste `member` in `memberlist`), oder auf einen Wert, der um eins größer als die des unmittelbar vorangehenden `member`.</span><span class="sxs-lookup"><span data-stu-id="9b713-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="9b713-171">In jedem bereitgestellten Ausdruck `initializer` kann eine beliebige Kombination von Literalen, andere, bereits definierte, Konstanten und Enumerationsmember, der bereits definiert sind, einschließlich eines vorherigen Members dieser Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9b713-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="9b713-172">Sie können arithmetische und logische Operatoren verwenden, zur Kombination dieser Elemente.</span><span class="sxs-lookup"><span data-stu-id="9b713-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="9b713-173">Sie können keine Variablen oder Funktionen in `initializer`.</span><span class="sxs-lookup"><span data-stu-id="9b713-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="9b713-174">Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`.</span><span class="sxs-lookup"><span data-stu-id="9b713-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="9b713-175">Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` -Argument, das zum Zeitpunkt der Kompilierung ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="9b713-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="9b713-176">Enumerationen können keine Gleitkommawerte haben.</span><span class="sxs-lookup"><span data-stu-id="9b713-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="9b713-177">Wenn ein Element einen Gleitkommawert zugewiesen ist und `Option Strict` auf on festgelegt ist, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="9b713-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="9b713-178">Wenn `Option Strict` deaktiviert ist, wird automatisch konvertierte Wert der `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="9b713-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="9b713-179">Wenn der Wert eines Members den für den zugrunde liegenden Datentyp zulässigen Bereich überschreitet oder Member, die von den zugrunde liegenden Datentyp zulässigen Höchstwert initialisiert, meldet der Compiler einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="9b713-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="9b713-180">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="9b713-180">Modifiers</span></span>  
 <span data-ttu-id="9b713-181">Klasse, Struktur, Modul und Schnittstellenmember Enumerationen standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="9b713-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="9b713-182">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="9b713-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="9b713-183">Namespace Member Enumerationen standardmäßig Friend-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="9b713-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="9b713-184">Sie können ihre Zugriffsebenen auf öffentlich, jedoch nicht auf private oder geschützte anpassen.</span><span class="sxs-lookup"><span data-stu-id="9b713-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="9b713-185">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9b713-185">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="9b713-186">Alle Enumerationsmember haben Public-Zugriff und können keine Zugriffsmodifizierer auf diesen.</span><span class="sxs-lookup"><span data-stu-id="9b713-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="9b713-187">Wenn die Enumeration selbst eine restriktivere Zugriffsebene verfügt, hat die Zugriffsebene für die angegebene Enumeration jedoch Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="9b713-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="9b713-188">Standardmäßig sind alle Enumerationen Typen und ihre Felder sind Konstanten.</span><span class="sxs-lookup"><span data-stu-id="9b713-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="9b713-189">Aus diesem Grund die `Shared`, `Static`, und `ReadOnly` Schlüsselwörter können nicht verwendet werden, bei der Deklaration einer Enumeration oder ihrer Member.</span><span class="sxs-lookup"><span data-stu-id="9b713-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="9b713-190">Zuweisen mehrerer Werte</span><span class="sxs-lookup"><span data-stu-id="9b713-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="9b713-191">Enumerationen werden in der Regel sich gegenseitig ausschließende Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="9b713-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="9b713-192">Durch Einschließen der <xref:System.FlagsAttribute>Attribut in die `Enum` Deklaration können Sie stattdessen Zuweisen mehrerer Werte eine Instanz der Enumeration.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9b713-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="9b713-193">Die <xref:System.FlagsAttribute>Attribut gibt an, dass die Enumeration als Bitfeld, d. h. als Gruppe von Flags behandelt werden.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9b713-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="9b713-194">Diese heißen *bitweise* Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="9b713-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="9b713-195">Wenn Sie eine Enumeration deklarieren, indem die <xref:System.FlagsAttribute>-Attribut, wird empfohlen, für die Werte Potenzen von 2, die ist, 1, 2, 4, 8, 16 und usw. verwenden.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9b713-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="9b713-196">Außerdem wird empfohlen, dass "None" der Name eines Elements, dessen Wert 0 ist.</span><span class="sxs-lookup"><span data-stu-id="9b713-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="9b713-197">Weitere Richtlinien finden Sie unter <xref:System.FlagsAttribute>und <xref:System.Enum>.</xref:System.Enum> </xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9b713-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b713-198">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b713-198">Example</span></span>  
 <span data-ttu-id="9b713-199">Das folgende Beispiel zeigt, wie Sie die `Enum` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9b713-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="9b713-200">Hinweis, der das Element so genannte `EggSizeEnum.Medium`, und nicht als `Medium`.</span><span class="sxs-lookup"><span data-stu-id="9b713-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 <span data-ttu-id="9b713-201">[!code-vb[VbEnumsTask&#41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b713-201">[!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b713-202">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b713-202">Example</span></span>  
 <span data-ttu-id="9b713-203">Die Methode im folgenden Beispiel befindet sich außerhalb der `Egg` Klasse.</span><span class="sxs-lookup"><span data-stu-id="9b713-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="9b713-204">Aus diesem Grund `EggSizeEnum` vollqualifiziert als `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="9b713-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 <span data-ttu-id="9b713-205">[!code-vb[VbEnumsTask&#42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b713-205">[!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b713-206">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b713-206">Example</span></span>  
 <span data-ttu-id="9b713-207">Im folgenden Beispiel wird die `Enum` Anweisung, um eine Gruppe von verwandten definieren benannte Konstanten.</span><span class="sxs-lookup"><span data-stu-id="9b713-207">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="9b713-208">In diesem Fall sind die Werte Farben, die Sie zum Entwerfen von Dateneingabeformularen für eine Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9b713-208">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 <span data-ttu-id="9b713-209">[!code-vb[VbEnumsTask&#30;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b713-209">[!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b713-210">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b713-210">Example</span></span>  
 <span data-ttu-id="9b713-211">Das folgende Beispiel zeigt die Werte, die positive und negative Zahlen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9b713-211">The following example shows values that include both positive and negative numbers.</span></span>  
  
 <span data-ttu-id="9b713-212">[!code-vb[VbEnumsTask&#31;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b713-212">[!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b713-213">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b713-213">Example</span></span>  
 <span data-ttu-id="9b713-214">Im folgenden Beispiel ein `As` -Klausel zur Angabe der `datatype` einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9b713-214">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 <span data-ttu-id="9b713-215">[!code-vb[VbEnumsTask&6;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b713-215">[!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b713-216">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b713-216">Example</span></span>  
 <span data-ttu-id="9b713-217">Im folgenden Beispiel wird veranschaulicht, wie eine bitweise Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b713-217">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="9b713-218">Eine Instanz einer Enumeration bitweise können mehrere Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9b713-218">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="9b713-219">Die `Enum` Deklaration enthält die <xref:System.FlagsAttribute>Attribut, das angibt, dass die Enumeration als Satz von Flags behandelt werden kann.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9b713-219">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 <span data-ttu-id="9b713-220">[!code-vb[VbEnumsTask&#61;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b713-220">[!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b713-221">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b713-221">Example</span></span>  
 <span data-ttu-id="9b713-222">Im folgende Beispiel wird eine Enumeration durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9b713-222">The following example iterates through an enumeration.</span></span> <span data-ttu-id="9b713-223">Verwendet die <xref:System.Enum.GetNames%2A>Methode, um ein Array von Elementnamen aus der-Enumeration abzurufen und <xref:System.Enum.GetValues%2A>zum Abrufen eines Arrays der Memberwerte.</xref:System.Enum.GetValues%2A> </xref:System.Enum.GetNames%2A></span><span class="sxs-lookup"><span data-stu-id="9b713-223">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 <span data-ttu-id="9b713-224">[!code-vb[VbEnumsTask&51;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b713-224">[!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b713-225">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b713-225">See Also</span></span>  
 <span data-ttu-id="9b713-226"><xref:System.Enum></xref:System.Enum></span><span class="sxs-lookup"><span data-stu-id="9b713-226"><xref:System.Enum></span></span>   
 <span data-ttu-id="9b713-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="9b713-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
<span data-ttu-id="9b713-228"> [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9b713-228"> [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="9b713-229"> [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9b713-229"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="9b713-230"> [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="9b713-230"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="9b713-231"> [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="9b713-231"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="9b713-232"> [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="9b713-232"> [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

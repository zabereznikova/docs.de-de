---
title: Signaturen (F#)
description: "Erfahren Sie, wie eine Signaturdatei f# zu verwenden, um Informationen zu den öffentlichen Signaturen einer Reihe von F#-Programmelementen, z. B. Typen, Namespaces und Modulen aufzunehmen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 76c84a62-b2f6-44ec-8238-e687e2f7d18e
ms.openlocfilehash: d0f71c6472852268303a2d3af2e4b0a3c256704e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="signatures"></a><span data-ttu-id="09cd7-104">Signaturen</span><span class="sxs-lookup"><span data-stu-id="09cd7-104">Signatures</span></span>

<span data-ttu-id="09cd7-105">Eine Signaturdatei enthält Informationen zu den öffentlichen Signaturen einer Reihe von F#-Programmelementen wie Typen, Namespaces und Modulen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-105">A signature file contains information about the public signatures of a set of F# program elements, such as types, namespaces, and modules.</span></span> <span data-ttu-id="09cd7-106">Mit ihr kann der Zugriff auf diese Programmelemente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="09cd7-106">It can be used to specify the accessibility of these program elements.</span></span>


## <a name="remarks"></a><span data-ttu-id="09cd7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09cd7-107">Remarks</span></span>
<span data-ttu-id="09cd7-108">Für jede F#-Codedatei kann eine *Signaturdatei*vorhanden sein. Diese hat den gleichen Namen wie die Codedatei, aber die Erweiterung FSI statt FS.</span><span class="sxs-lookup"><span data-stu-id="09cd7-108">For each F# code file, you can have a *signature file*, which is a file that has the same name as the code file but with the extension .fsi instead of .fs.</span></span> <span data-ttu-id="09cd7-109">Signaturdateien können auch der Kompilierungsbefehlszeile hinzugefügt werden, wenn Sie die Befehlszeile direkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="09cd7-109">Signature files can also be added to the compilation command-line if you are using the command line directly.</span></span> <span data-ttu-id="09cd7-110">Für die Unterscheidung zwischen Codedateien und Signaturdateien werden Codedateien manchmal als *Implementierungsdateien*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="09cd7-110">To distinguish between code files and signature files, code files are sometimes referred to as *implementation files*.</span></span> <span data-ttu-id="09cd7-111">In einem Projekt sollte die Signaturdatei der zugeordneten Codedatei vorausgehen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-111">In a project, the signature file should precede the associated code file.</span></span>

<span data-ttu-id="09cd7-112">Eine Signaturdatei beschreibt die Namespaces, Module, Typen und Member in der entsprechenden Implementierungsdatei.</span><span class="sxs-lookup"><span data-stu-id="09cd7-112">A signature file describes the namespaces, modules, types, and members in the corresponding implementation file.</span></span> <span data-ttu-id="09cd7-113">Mithilfe der Informationen in einer Signaturdatei geben Sie an, auf welche Teile des Codes in der entsprechenden Implementierungsdatei von Code außerhalb der Implementierungsdatei zugegriffen werden kann und welche Teile interner Code der Implementierungsdatei sind.</span><span class="sxs-lookup"><span data-stu-id="09cd7-113">You use the information in a signature file to specify what parts of the code in the corresponding implementation file can be accessed from code outside the implementation file, and what parts are internal to the implementation file.</span></span> <span data-ttu-id="09cd7-114">Die Namespaces, Module und Typen in der Signaturdatei müssen eine Teilmenge der Namespaces, Module und Typen in der Implementierungsdatei sein.</span><span class="sxs-lookup"><span data-stu-id="09cd7-114">The namespaces, modules, and types that are included in the signature file must be a subset of the namespaces, modules, and types that are included in the implementation file.</span></span> <span data-ttu-id="09cd7-115">Abgesehen von einigen weiter unten in diesem Thema genannten Ausnahmen werden die Sprachelemente, die nicht in der Signaturdatei aufgeführt sind, als private Elemente der Implementierungsdatei betrachtet.</span><span class="sxs-lookup"><span data-stu-id="09cd7-115">With some exceptions noted later in this topic, those language elements that are not listed in the signature file are considered private to the implementation file.</span></span> <span data-ttu-id="09cd7-116">Wenn im Projekt oder der Befehlszeile keine Signaturdatei gefunden wird, wird Standardzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="09cd7-116">If no signature file is found in the project or command line, the default accessibility is used.</span></span>

<span data-ttu-id="09cd7-117">Weitere Informationen zum Standardzugriff finden Sie unter [Access Control](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="09cd7-117">For more information about the default accessibility, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="09cd7-118">In einer Signaturdatei werden die Definition der Typen und die Implementierungen der einzelnen Methoden oder Funktionen nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="09cd7-118">In a signature file, you do not repeat the definition of the types and the implementations of each method or function.</span></span> <span data-ttu-id="09cd7-119">Stattdessen verwenden Sie die Signatur für die jeweilige Methode bzw. Funktion, die als vollständige Spezifikation der von einem Modul- oder Namespacefragment implementierten Funktionalität fungiert.</span><span class="sxs-lookup"><span data-stu-id="09cd7-119">Instead, you use the signature for each method and function, which acts as a complete specification of the functionality that is implemented by a module or namespace fragment.</span></span> <span data-ttu-id="09cd7-120">Die Syntax für eine Typsignatur ist mit der in abstrakten Methodendeklarationen in Schnittstellen und abstrakten Klassen verwendeten Syntax identisch. Sie wird auch von IntelliSense und dem F#-Interpreter "fsi.exe" dargestellt, wenn dieser eine ordnungsgemäß kompilierte Eingabe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="09cd7-120">The syntax for a type signature is the same as that used in abstract method declarations in interfaces and abstract classes, and is also shown by IntelliSense and by the F# interpreter fsi.exe when it displays correctly compiled input.</span></span>

<span data-ttu-id="09cd7-121">Wenn die Informationen in der Typsignatur nicht ausreichen, um anzugeben, ob ein Typ versiegelt oder ein Schnittstellentyp ist, müssen Sie ein Attribut hinzufügen, das für den Compiler die Art des Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="09cd7-121">If there is not enough information in the type signature to indicate whether a type is sealed, or whether it is an interface type, you must add an attribute that indicates the nature of the type to the compiler.</span></span> <span data-ttu-id="09cd7-122">Zu diesem Zweck verwendete Attribute werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="09cd7-122">Attributes that you use for this purpose are described in the following table.</span></span>



|<span data-ttu-id="09cd7-123">Attribut</span><span class="sxs-lookup"><span data-stu-id="09cd7-123">Attribute</span></span>|<span data-ttu-id="09cd7-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09cd7-124">Description</span></span>|
|---------|-----------|
|`[<Sealed>]`|<span data-ttu-id="09cd7-125">Für einen Typ, der über keine abstrakten Member verfügt oder nicht erweitert werden darf.</span><span class="sxs-lookup"><span data-stu-id="09cd7-125">For a type that has no abstract members, or that should not be extended.</span></span>|
|`[<Interface>]`|<span data-ttu-id="09cd7-126">Für einen Typ, der eine Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="09cd7-126">For a type that is an interface.</span></span>|
<span data-ttu-id="09cd7-127">Der Compiler erzeugt einen Fehler, wenn die Attribute in der Signatur und der Deklaration in der Implementierungsdatei nicht konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="09cd7-127">The compiler produces an error if the attributes are not consistent between the signature and the declaration in the implementation file.</span></span>

<span data-ttu-id="09cd7-128">Erstellen Sie mithilfe des Schlüsselworts `val` eine Signatur für einen Wert oder einen Funktionswert.</span><span class="sxs-lookup"><span data-stu-id="09cd7-128">Use the keyword `val` to create a signature for a value or function value.</span></span> <span data-ttu-id="09cd7-129">Mit dem Schlüsselwort `type` wird eine Typsignatur eingeführt.</span><span class="sxs-lookup"><span data-stu-id="09cd7-129">The keyword `type` introduces a type signature.</span></span>

<span data-ttu-id="09cd7-130">Sie können mit der `--sig` -Compileroption eine Signaturdatei generieren.</span><span class="sxs-lookup"><span data-stu-id="09cd7-130">You can generate a signature file by using the `--sig` compiler option.</span></span> <span data-ttu-id="09cd7-131">Im Allgemeinen werden FSI-Dateien nicht manuell geschrieben.</span><span class="sxs-lookup"><span data-stu-id="09cd7-131">Generally, you do not write .fsi files manually.</span></span> <span data-ttu-id="09cd7-132">Stattdessen generieren Sie FSI-Dateien mit dem Compiler, fügen sie ggf. dem Projekt hinzu und bearbeiten sie, indem Sie Methoden und Funktionen entfernen, auf die kein Zugriff möglich sein soll.</span><span class="sxs-lookup"><span data-stu-id="09cd7-132">Instead, you generate .fsi files by using the compiler, add them to your project, if you have one, and edit them by removing methods and functions that you do not want to be accessible.</span></span>

<span data-ttu-id="09cd7-133">Für Typsignaturen gelten mehrere Regeln:</span><span class="sxs-lookup"><span data-stu-id="09cd7-133">There are several rules for type signatures:</span></span>


- <span data-ttu-id="09cd7-134">Typabkürzungen in einer Implementierungsdatei dürfen keinem Typ ohne Abkürzung in einer Signaturdatei entsprechen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-134">Type abbreviations in an implementation file must not match a type without an abbreviation in a signature file.</span></span>


- <span data-ttu-id="09cd7-135">Datensätze und Unterscheidungs-Unions müssen entweder alle oder keine der zugehörigen Felder und Konstruktoren verfügbar machen, und die Reihenfolge in der Signatur muss mit der Reihenfolge in der Implementierungsdatei übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-135">Records and discriminated unions must expose either all or none of their fields and constructors, and the order in the signature must match the order in the implementation file.</span></span> <span data-ttu-id="09cd7-136">Klassen können einige, alle oder keine ihrer Felder und Methoden in der Signatur offenlegen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-136">Classes can reveal some, all, or none of their fields and methods in the signature.</span></span>


- <span data-ttu-id="09cd7-137">Klassen und Strukturen, die über Konstruktoren verfügen, müssen die Deklarationen ihrer Basisklassen (die `inherits` -Deklaration) verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-137">Classes and structures that have constructors must expose the declarations of their base classes (the `inherits` declaration).</span></span> <span data-ttu-id="09cd7-138">Klassen und Strukturen, die über Konstruktoren verfügen, müssen außerdem alle ihre abstrakten Methoden und Schnittstellendeklarationen verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-138">Also, classes and structures that have constructors must expose all of their abstract methods and interface declarations.</span></span>


- <span data-ttu-id="09cd7-139">Schnittstellentypen müssen alle ihre Methoden und Schnittstellen offenlegen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-139">Interface types must reveal all their methods and interfaces.</span></span>


<span data-ttu-id="09cd7-140">Für Wertsignaturen gelten folgende Regeln:</span><span class="sxs-lookup"><span data-stu-id="09cd7-140">The rules for value signatures are as follows:</span></span>


- <span data-ttu-id="09cd7-141">Zugriffsmodifizierer (`public`, `internal`usw.) sowie der `inline` -Modifizierer und der `mutable` -Modifizierer in der Signatur müssen mit den entsprechenden Modifizierern in der Implementierung übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-141">Modifiers for accessibility (`public`, `internal`, and so on) and the `inline` and `mutable` modifiers in the signature must match those in the implementation.</span></span>


- <span data-ttu-id="09cd7-142">Die Anzahl der generischen Typparameter (implizit abgeleitet oder explizit deklariert) muss übereinstimmen, und die Typen und Typeinschränkungen in generischen Typparametern müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="09cd7-142">The number of generic type parameters (either implicitly inferred or explicitly declared) must match, and the types and type constraints in generic type parameters must match.</span></span>


- <span data-ttu-id="09cd7-143">Wenn das `Literal` -Attribut verwendet wird, muss es sowohl in der Signatur als auch in der Implementierung erscheinen, und für beide muss der gleiche Literalwert verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="09cd7-143">If the `Literal` attribute is used, it must appear in both the signature and the implementation, and the same literal value must be used for both.</span></span>


- <span data-ttu-id="09cd7-144">Das Muster der Parameter (auch *Stelligkeit*) von Signaturen und Implementierungen muss konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="09cd7-144">The pattern of parameters (also known as the *arity*) of signatures and implementations must be consistent.</span></span>


<span data-ttu-id="09cd7-145">Das folgende Codebeispiel veranschaulicht eine Signaturdatei, die Namespace-, Modul-, Funktionswert- und Typsignaturen sowie die entsprechenden Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="09cd7-145">The following code example shows an example of a signature file that has namespace, module, function value, and type signatures together with the appropriate attributes.</span></span> <span data-ttu-id="09cd7-146">Im Beispiel wird außerdem die entsprechende Implementierungsdatei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="09cd7-146">It also shows the corresponding implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9002.fs)]

<span data-ttu-id="09cd7-147">Im folgenden Code wird die Implementierungsdatei veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="09cd7-147">The following code shows the implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9001.fs)]
    
## <a name="see-also"></a><span data-ttu-id="09cd7-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09cd7-148">See Also</span></span>
[<span data-ttu-id="09cd7-149">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="09cd7-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="09cd7-150">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="09cd7-150">Access Control</span></span>](access-control.md)

[<span data-ttu-id="09cd7-151">Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="09cd7-151">Compiler Options</span></span>](compiler-options.md)

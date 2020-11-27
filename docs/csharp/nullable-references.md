---
title: Nullwerte zulassende Verweistypen
description: Dieser Artikel bietet eine Übersicht der Nullable-Verweistypen, die in C# 8.0 hinzugefügt wurden. Sie erfahren, wie das Feature bei neuen und vorhandenen Projekten vor Nullverweisausnahmen schützt.
ms.technology: csharp-null-safety
ms.date: 04/21/2020
ms.openlocfilehash: b4906987ee23f458c1da9754ed7b402621169f63
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099339"
---
# <a name="nullable-reference-types"></a><span data-ttu-id="8e238-104">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="8e238-104">Nullable reference types</span></span>

<span data-ttu-id="8e238-105">Mit den in C# 8.0 eingeführten **Nullable-Verweistypen** und **Nicht-Nullable-Verweistypen** können Sie wichtige Anweisungen zu den Eigenschaften für Verweistypvariablen erstellen:</span><span class="sxs-lookup"><span data-stu-id="8e238-105">C# 8.0 introduces **nullable reference types** and **non-nullable reference types** that enable you to make important statements about the properties for reference type variables:</span></span>

- <span data-ttu-id="8e238-106">**Ein Verweis darf nicht NULL sein**.</span><span class="sxs-lookup"><span data-stu-id="8e238-106">**A reference isn't supposed to be null**.</span></span> <span data-ttu-id="8e238-107">Wenn Variablen nicht NULL sein dürfen, erzwingt der Compiler Regeln, die sicherstellen, dass das Dereferenzieren dieser Variablen sicher ist, ohne zuerst zu überprüfen, dass sie nicht NULL sind:</span><span class="sxs-lookup"><span data-stu-id="8e238-107">When variables aren't supposed to be null, the compiler enforces rules that ensure it's safe to dereference these variables without first checking that it isn't null:</span></span>
  - <span data-ttu-id="8e238-108">Die Variable muss mit einem Wert ungleich NULL initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-108">The variable must be initialized to a non-null value.</span></span>
  - <span data-ttu-id="8e238-109">Der Variablen kann nie der Wert `null` zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-109">The variable can never be assigned the value `null`.</span></span>
- <span data-ttu-id="8e238-110">**Ein Verweis darf NULL sein**.</span><span class="sxs-lookup"><span data-stu-id="8e238-110">**A reference may be null**.</span></span> <span data-ttu-id="8e238-111">Wenn Variablen NULL sein dürfen, erzwingt der Compiler verschiedene Regeln, um sicherzustellen, dass Sie richtig auf einen Nullverweis überprüft haben:</span><span class="sxs-lookup"><span data-stu-id="8e238-111">When variables may be null, the compiler enforces different rules to ensure that you've correctly checked for a null reference:</span></span>
  - <span data-ttu-id="8e238-112">Die Variable kann nur dereferenziert werden, wenn der Compiler garantieren kann, dass der Wert nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8e238-112">The variable may only be dereferenced when the compiler can guarantee that the value isn't null.</span></span>
  - <span data-ttu-id="8e238-113">Diese Variablen können mit dem Standardwert `null` initialisiert und in anderem Code dem Wert `null` zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-113">These variables may be initialized with the default `null` value and may be assigned the value `null` in other code.</span></span>

<span data-ttu-id="8e238-114">Dieses neue Feature bietet große Vorteile hinsichtlich der Verarbeitung von Verweisvariablen in früheren Versionen von C#, bei denen die Entwurfsabsicht nicht über die Variablendeklaration bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8e238-114">This new feature provides significant benefits over the handling of reference variables in earlier versions of C# where the design intent can't be determined from the variable declaration.</span></span> <span data-ttu-id="8e238-115">Der Compiler bot keinen Schutz gegen Nullverweisausnahmen für Verweistypen:</span><span class="sxs-lookup"><span data-stu-id="8e238-115">The compiler didn't provide safety against null reference exceptions for reference types:</span></span>

- <span data-ttu-id="8e238-116">**Ein Verweis kann NULL sein**.</span><span class="sxs-lookup"><span data-stu-id="8e238-116">**A reference can be null**.</span></span> <span data-ttu-id="8e238-117">Wenn eine Verweistypvariable mit `null` initialisiert oder später `null` zugewiesen wird, gibt der Compiler keine Warnungen aus.</span><span class="sxs-lookup"><span data-stu-id="8e238-117">The compiler doesn't issue warnings when a reference-type variable is initialized to `null`, or later assigned `null`.</span></span> <span data-ttu-id="8e238-118">Der Compiler gibt Warnungen aus, wenn diese Variablen ohne NULL-Überprüfungen dereferenziert werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-118">The compiler issues warnings when these variables are dereferenced without null checks.</span></span>
- <span data-ttu-id="8e238-119">**Es wird angenommen, dass ein Verweis nicht NULL ist**.</span><span class="sxs-lookup"><span data-stu-id="8e238-119">**A reference is assumed to be not null**.</span></span> <span data-ttu-id="8e238-120">Der Compiler gibt keine Warnungen aus, wenn Verweistypen dereferenziert werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-120">The compiler doesn't issue any warnings when reference types are dereferenced.</span></span> <span data-ttu-id="8e238-121">Der Compiler gibt Warnungen aus, wenn eine Variable auf einen Ausdruck festgelegt ist, der NULL sein kann.</span><span class="sxs-lookup"><span data-stu-id="8e238-121">The compiler issues warnings if a variable is set to an expression that may be null.</span></span>

<span data-ttu-id="8e238-122">Diese Warnungen werden zum Zeitpunkt der Kompilierung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e238-122">These warnings are emitted at compile time.</span></span> <span data-ttu-id="8e238-123">Der Compiler fügt keine NULL-Überprüfungen oder andere Laufzeitkonstrukte in einem Nullable-Kontext hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e238-123">The compiler doesn't add any null checks or other runtime constructs in a nullable context.</span></span> <span data-ttu-id="8e238-124">Zur Laufzeit sind ein Nullable-Verweis und ein Non-Nullable-Verweis gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="8e238-124">At runtime, a nullable reference and a non-nullable reference are equivalent.</span></span>

<span data-ttu-id="8e238-125">Durch das Hinzufügen von Nullable-Verweistypen können Sie Ihre Absicht klarer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8e238-125">With the addition of nullable reference types, you can declare your intent more clearly.</span></span> <span data-ttu-id="8e238-126">Der `null`-Wert ist die richtige Wahl, um darzustellen, dass eine Variable auf keinen Wert verweist.</span><span class="sxs-lookup"><span data-stu-id="8e238-126">The `null` value is the correct way to represent that a variable doesn't refer to a value.</span></span> <span data-ttu-id="8e238-127">Verwenden Sie dieses Feature nicht dazu, alle `null`-Werte aus Ihrem Code zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8e238-127">Don't use this feature to remove all `null` values from your code.</span></span> <span data-ttu-id="8e238-128">Stattdessen sollten Sie Ihre Absicht gegenüber dem Compiler und anderen Entwicklern deklarieren, die Ihren Code lesen.</span><span class="sxs-lookup"><span data-stu-id="8e238-128">Rather, you should declare your intent to the compiler and other developers that read your code.</span></span> <span data-ttu-id="8e238-129">Indem Sie Ihre Absicht deklarieren, werden Sie vom Compiler informiert, sobald Sie Code schreiben, der dieser Absicht widerspricht.</span><span class="sxs-lookup"><span data-stu-id="8e238-129">By declaring your intent, the compiler informs you when you write code that is inconsistent with that intent.</span></span>

<span data-ttu-id="8e238-130">Ein **Nullable-Verweistyp** wird mithilfe der gleichen Syntax wie [Nullable-Werttypen](language-reference/builtin-types/nullable-value-types.md) aufgeführt: Ein `?` wird an den Variablentyp angefügt.</span><span class="sxs-lookup"><span data-stu-id="8e238-130">A **nullable reference type** is noted using the same syntax as [nullable value types](language-reference/builtin-types/nullable-value-types.md): a `?` is appended to the type of the variable.</span></span> <span data-ttu-id="8e238-131">Beispielsweise stellt die folgende Variablendeklaration eine Nullable-Zeichenfolgenvariable, `name`, dar:</span><span class="sxs-lookup"><span data-stu-id="8e238-131">For example, the following variable declaration represents a nullable string variable, `name`:</span></span>

```csharp
string? name;
```

<span data-ttu-id="8e238-132">Bei jeder Variable, bei der `?` nicht an den Typnamen angefügt ist, handelt es sich um einen **Non-Nullable-Verweistyp**.</span><span class="sxs-lookup"><span data-stu-id="8e238-132">Any variable where the `?` isn't appended to the type name is a **non-nullable reference type**.</span></span> <span data-ttu-id="8e238-133">Dies umfasst alle Verweistypvariablen in vorhandenem Code, wenn Sie dieses Feature aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="8e238-133">That includes all reference type variables in existing code when you've enabled this feature.</span></span>

<span data-ttu-id="8e238-134">Der Compiler verwendet die statische Analyse, um zu bestimmen, ob ein Nullable-Verweis nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8e238-134">The compiler uses static analysis to determine if a nullable reference is known to be non-null.</span></span> <span data-ttu-id="8e238-135">Der Compiler warnt Sie, falls Sie einen Nullable-Verweis dereferenzieren, wenn dieser möglicherweise NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8e238-135">The compiler warns you if you dereference a nullable reference when it may be null.</span></span> <span data-ttu-id="8e238-136">Sie können dieses Verhalten überschreiben, indem Sie den [NULL-toleranten Operator](language-reference/operators/null-forgiving.md) (`!`) gefolgt von einem Variablennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e238-136">You can override this behavior by using the [null-forgiving operator](language-reference/operators/null-forgiving.md) `!` following a variable name.</span></span> <span data-ttu-id="8e238-137">Wenn Sie beispielsweise wissen, dass die Variable `name` nicht NULL ist, der Compiler aber eine Warnung ausgibt, können Sie folgenden Code schreiben, um die Compileranalyse zu überschreiben:</span><span class="sxs-lookup"><span data-stu-id="8e238-137">For example, if you know the `name` variable isn't null but the compiler issues a warning, you can write the following code to override the compiler's analysis:</span></span>

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a><span data-ttu-id="8e238-138">NULL-Zulässigkeit von Typen</span><span class="sxs-lookup"><span data-stu-id="8e238-138">Nullability of types</span></span>

<span data-ttu-id="8e238-139">Jeder beliebige Verweistyp kann über eine von vier *NULL-Zulässigkeiten* verfügen, die beschreibt, wann Warnungen ausgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="8e238-139">Any reference type can have one of four *nullabilities*, which describes when warnings are generated:</span></span>

- <span data-ttu-id="8e238-140">*Nonnullable* (Nicht-Nullable): Variablen dieses Typs kann NULL nicht zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-140">*Nonnullable*: Null can't be assigned to variables of this type.</span></span> <span data-ttu-id="8e238-141">Variablen dieses Typs müssen vor der Dereferenzierung nicht auf NULL überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-141">Variables of this type don't need to be null-checked before dereferencing.</span></span>
- <span data-ttu-id="8e238-142">*Nullable*: Variablen dieses Typs kann NULL zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-142">*Nullable*: Null can be assigned to variables of this type.</span></span> <span data-ttu-id="8e238-143">Wenn Variablen dieses Typs dereferenziert werden, ohne dass zuvor auf `null` überprüft wurde, wird eine Warnung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e238-143">Dereferencing variables of this type without first checking for `null` causes a warning.</span></span>
- <span data-ttu-id="8e238-144">*Oblivious* (Nichtbeachtend): Oblivious ist der Zustand vor C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="8e238-144">*Oblivious*: Oblivious is the pre-C# 8.0 state.</span></span> <span data-ttu-id="8e238-145">Variablen dieses Typs können ohne Warnungen dereferenziert oder zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-145">Variables of this type can be dereferenced or assigned without warnings.</span></span>
- <span data-ttu-id="8e238-146">*Unknown* (Unbekannt): Unknown ist im Allgemeinen für Typparameter gedacht, bei denen der Compiler von Einschränkungen nicht erfährt, dass es sich bei dem Typ um einen *Nullable-* oder einen *Non-Nullable-Typ* handeln muss.</span><span class="sxs-lookup"><span data-stu-id="8e238-146">*Unknown*: Unknown is generally for type parameters where constraints don't tell the compiler that the type must be *nullable* or *nonnullable*.</span></span>

<span data-ttu-id="8e238-147">Die NULL-Zulässigkeit eines Typs in einer Variablendeklaration wird durch den *Nullable-Kontext* gesteuert, in der die Variable deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="8e238-147">The nullability of a type in a variable declaration is controlled by the *nullable context* in which the variable is declared.</span></span>

## <a name="nullable-contexts"></a><span data-ttu-id="8e238-148">Nullable-Kontexte</span><span class="sxs-lookup"><span data-stu-id="8e238-148">Nullable contexts</span></span>

<span data-ttu-id="8e238-149">Nullable-Kontexte ermöglichen eine differenzierte Steuerung der Interpretation von Verweistypvariablen durch den Compiler.</span><span class="sxs-lookup"><span data-stu-id="8e238-149">Nullable contexts enable fine-grained control for how the compiler interprets reference type variables.</span></span> <span data-ttu-id="8e238-150">Der **Nullable-Anmerkungskontext** jeder beliebigen Quellzeile ist aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8e238-150">The **nullable annotation context** of any given source line is either enabled or disabled.</span></span> <span data-ttu-id="8e238-151">Der Compiler vor C# 8.0 hat Ihren gesamten Code in einem deaktivierten Nullable-Kontext kompiliert: Jeder Verweistyp kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="8e238-151">You can think of the pre-C# 8.0 compiler as compiling all your code in a disabled nullable context: any reference type may be null.</span></span> <span data-ttu-id="8e238-152">Der **Kontext „nullable warnings“** (Nullable-Warnungen) kann ebenfalls aktiviert oder deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="8e238-152">The **nullable warnings context** may also be enabled or disabled.</span></span> <span data-ttu-id="8e238-153">Der Nullable-Warnungskontext gibt die vom Compiler generierten Warnungen mithilfe der Flussanalyse an.</span><span class="sxs-lookup"><span data-stu-id="8e238-153">The nullable warnings context specifies the warnings generated by the compiler using its flow analysis.</span></span>

<span data-ttu-id="8e238-154">Der Nullable-Anmerkungskontext und der Nullable-Warnungskontext können für ein Projekt festgelegt werden, indem Sie das `Nullable`-Element in Ihrer *CSPROJ*-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e238-154">The nullable annotation context and nullable warning context can be set for a project using the `Nullable` element in your *.csproj* file.</span></span> <span data-ttu-id="8e238-155">Dieses Element konfiguriert, wie der Compiler die NULL-Zulässigkeit von Typen interpretiert und welche Warnungen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-155">This element configures how the compiler interprets the nullability of types and what warnings are generated.</span></span> <span data-ttu-id="8e238-156">Gültige Einstellungen sind folgende:</span><span class="sxs-lookup"><span data-stu-id="8e238-156">Valid settings are:</span></span>

- <span data-ttu-id="8e238-157">`enable`: Der Nullable-Anmerkungskontext ist **enabled** (aktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-157">`enable`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="8e238-158">Der Nullable-Warnungskontext ist **enabled** (aktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-158">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="8e238-159">Variablen eines Verweistyps wie `string` sind „non-nullable“ (nicht-nullable).</span><span class="sxs-lookup"><span data-stu-id="8e238-159">Variables of a reference type, `string` for example, are non-nullable.</span></span>  <span data-ttu-id="8e238-160">Alle NULL-Zulässigkeitswarnungen sind „enabled“ (aktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-160">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="8e238-161">`warnings`: Der Nullable-Anmerkungskontext ist **disabled** (deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-161">`warnings`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="8e238-162">Der Nullable-Warnungskontext ist **enabled** (aktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-162">The nullable warning context is **enabled**.</span></span>
  - <span data-ttu-id="8e238-163">Variablen eines Verweistyps sind „oblivious“ (nichtbeachtend).</span><span class="sxs-lookup"><span data-stu-id="8e238-163">Variables of a reference type are oblivious.</span></span> <span data-ttu-id="8e238-164">Alle NULL-Zulässigkeitswarnungen sind „enabled“ (aktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-164">All nullability warnings are enabled.</span></span>
- <span data-ttu-id="8e238-165">`annotations`: Der Nullable-Anmerkungskontext ist **enabled** (aktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-165">`annotations`: The nullable annotation context is **enabled**.</span></span> <span data-ttu-id="8e238-166">Der Nullable-Warnungskontext ist **disabled** (deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-166">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="8e238-167">Variablen eines Verweistyps wie „string“ sind „non-nullable“ (nicht-nullable).</span><span class="sxs-lookup"><span data-stu-id="8e238-167">Variables of a reference type, string for example, are non-nullable.</span></span> <span data-ttu-id="8e238-168">Alle NULL-Zulässigkeitswarnungen sind „disabled“ (deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-168">All nullability warnings are disabled.</span></span>
- <span data-ttu-id="8e238-169">`disable`: Der Nullable-Anmerkungskontext ist **disabled** (deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-169">`disable`: The nullable annotation context is **disabled**.</span></span> <span data-ttu-id="8e238-170">Der Nullable-Warnungskontext ist **disabled** (deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-170">The nullable warning context is **disabled**.</span></span>
  - <span data-ttu-id="8e238-171">Variablen eines Verweistyps sind „oblivious“ (nichtbeachtend), wie in früheren Versionen von C#.</span><span class="sxs-lookup"><span data-stu-id="8e238-171">Variables of a reference type are oblivious, just like earlier versions of C#.</span></span> <span data-ttu-id="8e238-172">Alle NULL-Zulässigkeitswarnungen sind „disabled“ (deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="8e238-172">All nullability warnings are disabled.</span></span>

<span data-ttu-id="8e238-173">**Beispiel**:</span><span class="sxs-lookup"><span data-stu-id="8e238-173">**Example**:</span></span>

```xml
<Nullable>enable</Nullable>
```

<span data-ttu-id="8e238-174">Sie können auch Anweisungen verwenden, um diese Kontexte überall in Ihrem Projekt festzulegen:</span><span class="sxs-lookup"><span data-stu-id="8e238-174">You can also use directives to set these same contexts anywhere in your project:</span></span>

- <span data-ttu-id="8e238-175">`#nullable enable`: Legt den Nullable-Anmerkungskontext und den Nullable-Warnungskontext auf **enabled** (aktiviert) fest.</span><span class="sxs-lookup"><span data-stu-id="8e238-175">`#nullable enable`: Sets the nullable annotation context and nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="8e238-176">`#nullable disable`: Legt den Nullable-Anmerkungskontext und den Nullable-Warnungskontext auf **disabled** (deaktiviert) fest.</span><span class="sxs-lookup"><span data-stu-id="8e238-176">`#nullable disable`: Sets the nullable annotation context and nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="8e238-177">`#nullable restore`: Stellt die Projekteinstellungen für den Nullable-Anmerkungskontext und den Nullable-Warnungskontext wieder her.</span><span class="sxs-lookup"><span data-stu-id="8e238-177">`#nullable restore`: Restores the nullable annotation context and nullable warning context to the project settings.</span></span>
- <span data-ttu-id="8e238-178">`#nullable disable warnings`: Legt den Nullable-Warnungskontext auf **disabled** (deaktiviert) fest.</span><span class="sxs-lookup"><span data-stu-id="8e238-178">`#nullable disable warnings`: Set the nullable warning context to **disabled**.</span></span>
- <span data-ttu-id="8e238-179">`#nullable enable warnings`: Legt den Nullable-Warnungskontext auf **enabled** (aktiviert) fest.</span><span class="sxs-lookup"><span data-stu-id="8e238-179">`#nullable enable warnings`: Set the nullable warning context to **enabled**.</span></span>
- <span data-ttu-id="8e238-180">`#nullable restore warnings`: Stellt die Projekteinstellungen für den Nullable-Warnungskontext wieder her.</span><span class="sxs-lookup"><span data-stu-id="8e238-180">`#nullable restore warnings`: Restores the nullable warning context to the project settings.</span></span>
- <span data-ttu-id="8e238-181">`#nullable disable annotations`: Legt den Nullable-Anmerkungskontext auf **disabled** (deaktiviert) fest.</span><span class="sxs-lookup"><span data-stu-id="8e238-181">`#nullable disable annotations`: Set the nullable annotation context to **disabled**.</span></span>
- <span data-ttu-id="8e238-182">`#nullable enable annotations`: Legt den Nullable-Anmerkungskontext auf **enabled** (aktiviert) fest.</span><span class="sxs-lookup"><span data-stu-id="8e238-182">`#nullable enable annotations`: Set the nullable annotation context to **enabled**.</span></span>
- <span data-ttu-id="8e238-183">`#nullable restore annotations`: Stellt die Projekteinstellungen für den Anmerkungswarnungskontext wieder her.</span><span class="sxs-lookup"><span data-stu-id="8e238-183">`#nullable restore annotations`: Restores the annotation warning context to the project settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e238-184">Der globale Nullable-Kontext gilt nicht für generierte Codedateien.</span><span class="sxs-lookup"><span data-stu-id="8e238-184">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="8e238-185">Der Nullable-Kontext ist unabhängig von der Strategie für alle als generiert gekennzeichneten Quelldateien *deaktiviert*.</span><span class="sxs-lookup"><span data-stu-id="8e238-185">Under either strategy, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="8e238-186">Das bedeutet, dass alle in generierten Dateien enthaltenen APIs nicht mit Anmerkungen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-186">This means any APIs in generated files are not annotated.</span></span> <span data-ttu-id="8e238-187">Es gibt viel Möglichkeiten, eine Datei als generiert zu markieren:</span><span class="sxs-lookup"><span data-stu-id="8e238-187">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="8e238-188">Geben Sie in der EDITORCONFIG-Datei `generated_code = true` in einem Abschnitt an, der für diese Datei gilt.</span><span class="sxs-lookup"><span data-stu-id="8e238-188">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="8e238-189">Fügen Sie `<auto-generated>` oder `<auto-generated/>` ganz oben in der Datei in einem Kommentar ein.</span><span class="sxs-lookup"><span data-stu-id="8e238-189">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="8e238-190">Dabei kann es sich um eine beliebige Zeile des Kommentars handeln, jedoch muss es sich beim Kommentarblock um das erste Element in der Datei handeln.</span><span class="sxs-lookup"><span data-stu-id="8e238-190">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="8e238-191">Beginnen Sie den Dateinamen mit *TemporaryGeneratedFile_* .</span><span class="sxs-lookup"><span data-stu-id="8e238-191">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="8e238-192">Enden Sie den Dateinamen mit *.designer.cs*, *.generated.cs*, *.g.cs* oder *.g.i.cs*.</span><span class="sxs-lookup"><span data-stu-id="8e238-192">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="8e238-193">Generatoren können die Präprozessoranweisung [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e238-193">Generators can opt-in using the [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

<span data-ttu-id="8e238-194">Standardmäßig sind die Nullable-Anmerkungs- und -Warnungskontexte, einschließlich neuer Projekte, **deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="8e238-194">By default, nullable annotation and warning contexts are **disabled**, including new projects.</span></span> <span data-ttu-id="8e238-195">Dies bedeutet, dass Ihr vorhandener Code ohne Änderungen und ohne Warnungen kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="8e238-195">That means that your existing code compiles without changes and without generating any new warnings.</span></span>

<span data-ttu-id="8e238-196">Diese Optionen bieten zwei unterschiedliche Strategien zum [Aktualisieren einer vorhandenen Codebasis](nullable-migration-strategies.md), um Nullable-Verweistypen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e238-196">These options provide two distinct strategies to [update an existing codebase](nullable-migration-strategies.md) to use nullable reference types.</span></span>

## <a name="nullable-annotation-context"></a><span data-ttu-id="8e238-197">Nullable-Anmerkungskontext</span><span class="sxs-lookup"><span data-stu-id="8e238-197">Nullable annotation context</span></span>

<span data-ttu-id="8e238-198">Der Compiler verwendet die folgenden Regeln in einem „disabled“-Nullable-Anmerkungskontext:</span><span class="sxs-lookup"><span data-stu-id="8e238-198">The compiler uses the following rules in a disabled nullable annotation context:</span></span>

- <span data-ttu-id="8e238-199">Sie können keine Nullable-Verweise in einem „disabled“-Kontext deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8e238-199">You can't declare nullable references in a disabled context.</span></span>
- <span data-ttu-id="8e238-200">Alle Verweisvariablen kann ein Wert von NULL zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-200">All reference variables may be assigned a value of null.</span></span>
- <span data-ttu-id="8e238-201">Wenn eine Variable eines Verweistyps dereferenziert wird, werden keine Warnungen generiert.</span><span class="sxs-lookup"><span data-stu-id="8e238-201">No warnings are generated when a variable of a reference type is dereferenced.</span></span>
- <span data-ttu-id="8e238-202">Der NULL-tolerante Operator kann in einem „disabled“-Kontext nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-202">The null-forgiving operator may not be used in a disabled context.</span></span>

<span data-ttu-id="8e238-203">Das Verhalten ist wie bei früheren Versionen von C#.</span><span class="sxs-lookup"><span data-stu-id="8e238-203">The behavior is the same as previous versions of C#.</span></span>

<span data-ttu-id="8e238-204">Der Compiler verwendet die folgenden Regeln in einem „enabled“-Nullable-Anmerkungskontext:</span><span class="sxs-lookup"><span data-stu-id="8e238-204">The compiler uses the following rules in an enabled nullable annotation context:</span></span>

- <span data-ttu-id="8e238-205">Jede Variable eines Verweistyps ist ein **Nicht-Nullable-Verweis**.</span><span class="sxs-lookup"><span data-stu-id="8e238-205">Any variable of a reference type is a **non-nullable reference**.</span></span>
- <span data-ttu-id="8e238-206">Jeder Nicht-Nullable-Verweis kann sicher dereferenziert werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-206">Any non-nullable reference may be dereferenced safely.</span></span>
- <span data-ttu-id="8e238-207">Jeder Nullable-Verweistyp (aufgeführt durch `?` nach dem Typ in der Variablendeklaration) kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="8e238-207">Any nullable reference type (noted by `?` after the type in the variable declaration) may be null.</span></span> <span data-ttu-id="8e238-208">Durch die statische Analyse wird bestimmt, ob der Wert ungleich NULL ist, wenn er dereferenziert wird.</span><span class="sxs-lookup"><span data-stu-id="8e238-208">Static analysis determines if the value is known to be non-null when it's dereferenced.</span></span> <span data-ttu-id="8e238-209">Ist dies nicht der Fall, werden Sie vom Compiler gewarnt.</span><span class="sxs-lookup"><span data-stu-id="8e238-209">If not, the compiler warns you.</span></span>
- <span data-ttu-id="8e238-210">Sie können den NULL-toleranten Operator verwenden, um zu deklarieren, dass ein Nullable-Verweis nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8e238-210">You can use the null-forgiving operator to declare that a nullable reference isn't null.</span></span>

<span data-ttu-id="8e238-211">In einem „enabled“-Nullable-Anmerkungskontext deklariert das an einen Verweistyp angefügte Zeichen `?` einen **Nullable-Verweistyp**.</span><span class="sxs-lookup"><span data-stu-id="8e238-211">In an enabled nullable annotation context, the `?` character appended to a reference type declares a **nullable reference type**.</span></span> <span data-ttu-id="8e238-212">Der **NULL-tolerante Operator** (`!`) kann an einen Ausdruck angefügt werden, um zu deklarieren, dass der Ausdruck nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="8e238-212">The **null-forgiving operator** `!` may be appended to an expression to declare that the expression isn't null.</span></span>

## <a name="nullable-warning-context"></a><span data-ttu-id="8e238-213">Nullable-Warnungskontext</span><span class="sxs-lookup"><span data-stu-id="8e238-213">Nullable warning context</span></span>

<span data-ttu-id="8e238-214">Der Nullable-Warnungskontext unterscheidet sich vom Nullable-Anmerkungskontext.</span><span class="sxs-lookup"><span data-stu-id="8e238-214">The nullable warning context is distinct from the nullable annotation context.</span></span> <span data-ttu-id="8e238-215">Warnungen können selbst dann aktiviert sein, wenn die neuen Anmerkungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8e238-215">Warnings can be enabled even when the new annotations are disabled.</span></span> <span data-ttu-id="8e238-216">Der Compiler bestimmt mithilfe der statischen Flussanalyse den **NULL-Zustand** eines Verweises.</span><span class="sxs-lookup"><span data-stu-id="8e238-216">The compiler uses static flow analysis to determine the **null state** of any reference.</span></span> <span data-ttu-id="8e238-217">Der NULL-Zustand ist entweder **not null** (nicht NULL) oder **maybe null** (vielleicht NULL), wenn der *Nullable-Warnungskontext* nicht **disabled** (deaktiviert) ist.</span><span class="sxs-lookup"><span data-stu-id="8e238-217">The null state is either **not null** or **maybe null** when the *nullable warning context* isn't **disabled**.</span></span> <span data-ttu-id="8e238-218">Wenn Sie einen Verweis dereferenzieren, wenn der Compiler bestimmt hat, dass dessen Zustand **maybe null** (vielleicht NULL) lautet, löst der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="8e238-218">If you dereference a reference when the compiler has determined it's **maybe null**, the compiler warns you.</span></span> <span data-ttu-id="8e238-219">Der Status eines Verweises ist **maybe null** (vielleicht NULL), sofern der Compiler nicht eine der folgenden beiden Bedingungen bestimmen kann:</span><span class="sxs-lookup"><span data-stu-id="8e238-219">The state of a reference is **maybe null** unless the compiler can determine one of two conditions:</span></span>

1. <span data-ttu-id="8e238-220">Die Variable wurde definitiv einem Wert ungleich NULL zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8e238-220">The variable has been definitely assigned a non-null value.</span></span>
1. <span data-ttu-id="8e238-221">Die Variable oder der Ausdruck wurde vor der Dereferenzierung auf NULL überprüft.</span><span class="sxs-lookup"><span data-stu-id="8e238-221">The variable or expression has been checked against null before de-referencing it.</span></span>

<span data-ttu-id="8e238-222">Der Compiler generiert Warnungen, wenn Sie in einem Nullable-Warnungskontext eine Variable oder einen Ausdruck dereferenzieren, die oder der **vielleicht NULL** ist.</span><span class="sxs-lookup"><span data-stu-id="8e238-222">The compiler generates warnings when you dereference a variable or expression that is **maybe null** in a nullable warning context.</span></span> <span data-ttu-id="8e238-223">Darüber hinaus generiert der Compiler Warnungen, wenn einer Variable oder einem Ausdruck, die oder der **vielleicht NULL** ist, in einem aktivierten Nullable-Anmerkungskontext eine Non-Nullable-Verweistypvariable zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8e238-223">Furthermore, the compiler generates warnings when a nonnullable reference-type variable is assigned a **maybe null** variable or expression in an enabled nullable annotation context.</span></span>

## <a name="attributes-describe-apis"></a><span data-ttu-id="8e238-224">Beschreiben von APIs mit Attributen</span><span class="sxs-lookup"><span data-stu-id="8e238-224">Attributes describe APIs</span></span>

<span data-ttu-id="8e238-225">Sie fügen APIs Attribute hinzu, die für den Compiler weitere Informationen darüber bereitstellen, wann Argumente oder Rückgabewerte NULL sein können oder nicht.</span><span class="sxs-lookup"><span data-stu-id="8e238-225">You add attributes to APIs that provide the compiler more information about when arguments or return values can or can't be null.</span></span> <span data-ttu-id="8e238-226">Weitere Informationen zu diesen Attributen finden Sie in unserem Artikel in der Programmiersprachenreferenz zu den [Nullable-Attributen](language-reference/attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="8e238-226">You can learn more about these attributes in our article in the language reference covering the [nullable attributes](language-reference/attributes/nullable-analysis.md).</span></span> <span data-ttu-id="8e238-227">Diese Attribute werden über aktuelle und kommende Releases zu .NET-Bibliotheken hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8e238-227">These attributes are being added to .NET libraries over current and upcoming releases.</span></span> <span data-ttu-id="8e238-228">Die am häufigsten verwendeten APIs werden zuerst aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8e238-228">The most commonly used APIs are being updated first.</span></span>

## <a name="known-pitfalls"></a><span data-ttu-id="8e238-229">Bekannte Fehlerquellen</span><span class="sxs-lookup"><span data-stu-id="8e238-229">Known pitfalls</span></span>

<span data-ttu-id="8e238-230">Arrays und Strukturen, die Verweistypen enthalten, sind bekannte Fehlerquellen in Features, die NULL-Werte für Verweistypen zulassen.</span><span class="sxs-lookup"><span data-stu-id="8e238-230">Arrays and structs that contain reference types are known pitfalls in nullable reference types feature.</span></span>

### <a name="structs"></a><span data-ttu-id="8e238-231">Strukturen</span><span class="sxs-lookup"><span data-stu-id="8e238-231">Structs</span></span>

<span data-ttu-id="8e238-232">Strukturen, die Verweistypen enthalten, die keine NULL-Werte zulassen, können Sie `default` zuweisen, ohne dass Warnungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-232">A struct that contains non-nullable reference types allows assigning `default` for it without any warnings.</span></span> <span data-ttu-id="8e238-233">Betrachten Sie das folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e238-233">Consider the following example:</span></span>

```csharp
using System;

#nullable enable

public struct Student
{
    public string FirstName;
    public string? MiddleName;
    public string LastName;
}

public static class Program
{
    public static void PrintStudent(Student student)
    {
        Console.WriteLine($"First name: {student.FirstName.ToUpper()}");
        Console.WriteLine($"Middle name: {student.MiddleName.ToUpper()}");
        Console.WriteLine($"Last name: {student.LastName.ToUpper()}");
    }

    public static void Main() => PrintStudent(default);
}
```

<span data-ttu-id="8e238-234">Im obigen Beispiel gibt es in `PrintStudent(default)` keine Warnung, obwohl die Verweistypen `FirstName` und `LastName`, die keine NULL-Werte zulassen, NULL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8e238-234">In the preceding example, there is no warning in `PrintStudent(default)` while the non-nullable reference types `FirstName` and `LastName` are null.</span></span>

<span data-ttu-id="8e238-235">Bei der Verwendung von generischen Strukturen tritt ein weiteres häufigeres Problem auf.</span><span class="sxs-lookup"><span data-stu-id="8e238-235">Another more common case is when you deal with generic structs.</span></span> <span data-ttu-id="8e238-236">Betrachten Sie das folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e238-236">Consider the following example:</span></span>

```csharp
#nullable enable

public struct Foo<T>
{
    public T Bar { get; set; }
}

public static class Program
{
    public static void Main()
    {
        string s = default(Foo<string>).Bar;
    }
}
```

<span data-ttu-id="8e238-237">Im obigen Beispiel entspricht die Eigenschaft `Bar` zur Laufzeit `null`, und sie wird einer Zeichenfolge zugewiesen, die keine NULL-Werte zulässt, ohne dass eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8e238-237">In the preceding example, the property `Bar` is going to be `null` at runtime, and it's assigned to non-nullable string without any warnings.</span></span>

### <a name="arrays"></a><span data-ttu-id="8e238-238">Arrays</span><span class="sxs-lookup"><span data-stu-id="8e238-238">Arrays</span></span>

<span data-ttu-id="8e238-239">Arrays stellen ebenfalls eine bekannte Fehlerquelle in Verweistypen dar, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="8e238-239">Arrays are also a known pitfall in nullable reference types.</span></span> <span data-ttu-id="8e238-240">Sehen Sie sich das folgende Beispiel an, das keine Warnungen auslöst:</span><span class="sxs-lookup"><span data-stu-id="8e238-240">Consider the following example which doesn't produce any warnings:</span></span>

```csharp
using System;

#nullable enable

public static class Program
{
    public static void Main()
    {
        string[] values = new string[10];
        string s = values[0];
        Console.WriteLine(s.ToUpper());
    }
}
```

<span data-ttu-id="8e238-241">Im obigen Beispiel zeigt die Deklaration des Arrays, dass dieses Zeichenfolgen enthält, die keine NULL-Werte zulassen, während alle seine Elemente mit NULL-Werten initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e238-241">In the preceding example, the declaration of the array shows it holds non-nullable strings, while its elements are all initialized to null.</span></span> <span data-ttu-id="8e238-242">Anschließend wird der Variablen `s` ein NULL-Wert (das erste Element des Arrays) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8e238-242">Then, the variable `s` is assigned a null value (the first element of the array).</span></span> <span data-ttu-id="8e238-243">Schließlich wird die Variable `s` dereferenziert, was zu einer Laufzeitausnahme führt.</span><span class="sxs-lookup"><span data-stu-id="8e238-243">Finally, the variable `s` is dereferenced causing a runtime exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e238-244">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e238-244">See also</span></span>

- [<span data-ttu-id="8e238-245">Entwurf der Spezifikation für Nullable-Verweistypen</span><span class="sxs-lookup"><span data-stu-id="8e238-245">Draft nullable reference types specification</span></span>](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md)
- [<span data-ttu-id="8e238-246">Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="8e238-246">Intro to nullable references tutorial</span></span>](tutorials/nullable-reference-types.md)
- [<span data-ttu-id="8e238-247">Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="8e238-247">Migrate an existing codebase to nullable references</span></span>](tutorials/upgrade-to-nullable-references.md)
- [<span data-ttu-id="8e238-248">-nullable (C#-Compileroption)</span><span class="sxs-lookup"><span data-stu-id="8e238-248">-nullable (C# Compiler option)</span></span>](language-reference/compiler-options/nullable-compiler-option.md)

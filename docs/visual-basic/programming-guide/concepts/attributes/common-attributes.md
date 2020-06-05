---
title: Allgemeine Attribute
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 57ef8f103d64a51d896f46d2889d78ec99ff3223
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400718"
---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="3f30b-102">Common Attributes (Visual Basic) (Gemeinsame Attribute (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="3f30b-102">Common Attributes (Visual Basic)</span></span>

<span data-ttu-id="3f30b-103">In diesem Thema werden die Attribute beschrieben, die in Visual Basic Programmen am häufigsten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>

- [<span data-ttu-id="3f30b-104">Globale Attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-104">Global Attributes</span></span>](#Global)

- [<span data-ttu-id="3f30b-105">Obsolete-Attribut</span><span class="sxs-lookup"><span data-stu-id="3f30b-105">Obsolete Attribute</span></span>](#Obsolete)

- [<span data-ttu-id="3f30b-106">Conditional-Attribut</span><span class="sxs-lookup"><span data-stu-id="3f30b-106">Conditional Attribute</span></span>](#Conditional)

- [<span data-ttu-id="3f30b-107">Aufufrerinfoattribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-107">Caller Info Attributes</span></span>](#CallerInfo)

- [<span data-ttu-id="3f30b-108">Visual Basic Attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-108">Visual Basic Attributes</span></span>](#VB)

## <a name="global-attributes"></a><a name="Global"></a><span data-ttu-id="3f30b-109">Globale Attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-109">Global Attributes</span></span>

<span data-ttu-id="3f30b-110">Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – sie gelten für eine gesamte Assembly oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="3f30b-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="3f30b-111">Zum Beispiel kann das <xref:System.Reflection.AssemblyVersionAttribute>-Attribut zum Einbetten von Versionsinformationen in eine Assembly verwendet werden. Diese sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="3f30b-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

<span data-ttu-id="3f30b-112">Globale Attribute werden im Quellcode nach allen Anweisungen der obersten Ebene `Imports` und vor allen Typen-, Modul-oder Namespace Deklarationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f30b-112">Global attributes appear in the source code after any top-level `Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="3f30b-113">Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierungsdurchlauf kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="3f30b-114">Für Visual Basic Projekte werden globale Attribute in der Regel in die Datei AssemblyInfo. vb eingefügt (die Datei wird automatisch erstellt, wenn Sie ein Projekt in Visual Studio erstellen).</span><span class="sxs-lookup"><span data-stu-id="3f30b-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>

<span data-ttu-id="3f30b-115">Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="3f30b-116">Sie werden in die folgenden Kategorien eingeteilt:</span><span class="sxs-lookup"><span data-stu-id="3f30b-116">They fall into the following categories:</span></span>

- <span data-ttu-id="3f30b-117">Attribute für Assemblyidentitäten</span><span class="sxs-lookup"><span data-stu-id="3f30b-117">Assembly identity attributes</span></span>

- <span data-ttu-id="3f30b-118">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-118">Informational attributes</span></span>

- <span data-ttu-id="3f30b-119">Attribute für Assemblymanifeste.</span><span class="sxs-lookup"><span data-stu-id="3f30b-119">Assembly manifest attributes</span></span>

### <a name="assembly-identity-attributes"></a><span data-ttu-id="3f30b-120">Attribute für Assemblyidentitäten</span><span class="sxs-lookup"><span data-stu-id="3f30b-120">Assembly Identity Attributes</span></span>

<span data-ttu-id="3f30b-121">Drei Attribute bestimmen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: „name“, „version“ und „culture“.</span><span class="sxs-lookup"><span data-stu-id="3f30b-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="3f30b-122">Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf sie verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3f30b-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="3f30b-123">Mit Attributen können die Version und Kultur einer Assembly festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="3f30b-124">Allerdings wird der name-Wert vom Compiler, der Visual Studio-IDE im [Dialogfeld „Assemblyinformationen“](/visualstudio/ide/reference/assembly-information-dialog-box) oder dem Assemblylinker (Al.exe) festgelegt, wenn die Assembly erstellt wird. Die geschieht auf Grundlage der Datei, die das Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="3f30b-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="3f30b-125">Das Attribut <xref:System.Reflection.AssemblyFlagsAttribute> gibt an, ob mehrere Kopien der Assembly parallel bestehen können.</span><span class="sxs-lookup"><span data-stu-id="3f30b-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>

<span data-ttu-id="3f30b-126">In der folgenden Tabelle werden die Identitätsattribute aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3f30b-126">The following table shows the identity attributes.</span></span>

|<span data-ttu-id="3f30b-127">attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-127">Attribute</span></span>|<span data-ttu-id="3f30b-128">Zweck</span><span class="sxs-lookup"><span data-stu-id="3f30b-128">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="3f30b-129">Beschreibt vollständig die Identität einer Assembly</span><span class="sxs-lookup"><span data-stu-id="3f30b-129">Fully describes the identity of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="3f30b-130">Gibt die Version einer Assembly an</span><span class="sxs-lookup"><span data-stu-id="3f30b-130">Specifies the version of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="3f30b-131">Gibt an, welche Kultur die Assembly unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3f30b-131">Specifies which culture the assembly supports.</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="3f30b-132">Gibt an, ob eine Assembly die parallele Ausführung auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt</span><span class="sxs-lookup"><span data-stu-id="3f30b-132">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|

### <a name="informational-attributes"></a><span data-ttu-id="3f30b-133">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-133">Informational Attributes</span></span>

<span data-ttu-id="3f30b-134">Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-134">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="3f30b-135">Die folgende Tabelle zeigt die Informationsattribute, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-135">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="3f30b-136">attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-136">Attribute</span></span>|<span data-ttu-id="3f30b-137">Zweck</span><span class="sxs-lookup"><span data-stu-id="3f30b-137">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="3f30b-138">Definiert ein benutzerdefiniertes Attribut, das den Produktnamen für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-138">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="3f30b-139">Definiert ein benutzerdefiniertes Attribut, das eine Marke für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-139">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="3f30b-140">Definiert ein benutzerdefiniertes Attribut, das eine Informationsversion für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-140">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="3f30b-141">Definiert ein benutzerdefiniertes Attribut, das einen Firmennamen für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-141">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="3f30b-142">Definiert ein benutzerdefiniertes Attribut, das ein Copyright für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-142">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="3f30b-143">Weist den Compiler an, eine spezifische Versionsnummer für die Win32-Dateiversionsressource zu verwenden</span><span class="sxs-lookup"><span data-stu-id="3f30b-143">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="3f30b-144">Gibt an, ob die Assembly mit der Common Language Specification (CLS) kompatibel ist</span><span class="sxs-lookup"><span data-stu-id="3f30b-144">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|

### <a name="assembly-manifest-attributes"></a><span data-ttu-id="3f30b-145">Attribute für Assemblymanifeste</span><span class="sxs-lookup"><span data-stu-id="3f30b-145">Assembly Manifest Attributes</span></span>

<span data-ttu-id="3f30b-146">Sie können Attribute für Assemblymanifeste verwenden, um Informationen im Assemblymanifest bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-146">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="3f30b-147">Dies schließt Titel, Beschreibung, Standardalias und Konfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="3f30b-147">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="3f30b-148">Die folgende Tabelle zeigt die Attribute für Assemblymanifeste, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-148">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="3f30b-149">Attribut</span><span class="sxs-lookup"><span data-stu-id="3f30b-149">Attribute</span></span>|<span data-ttu-id="3f30b-150">Zweck</span><span class="sxs-lookup"><span data-stu-id="3f30b-150">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="3f30b-151">Definiert ein benutzerdefiniertes Attribut, das einen Assemblytitel für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-151">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="3f30b-152">Definiert ein benutzerdefiniertes Attribut, das eine Assemblybeschreibung für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-152">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="3f30b-153">Definiert ein benutzerdefiniertes Attribut, das eine Assemblykonfiguration (z.B. Retail oder Debug) für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="3f30b-153">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="3f30b-154">Definiert einen benutzerfreundlichen Standardalias für ein Assemblymanifest</span><span class="sxs-lookup"><span data-stu-id="3f30b-154">Defines a friendly default alias for an assembly manifest</span></span>|

## <a name="obsolete-attribute"></a><a name="Obsolete"></a><span data-ttu-id="3f30b-155">Veraltetes Attribut</span><span class="sxs-lookup"><span data-stu-id="3f30b-155">Obsolete Attribute</span></span>

<span data-ttu-id="3f30b-156">Das `Obsolete`-Attribut markiert eine Programmentität als eine, die nicht mehr zur Verwendung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="3f30b-156">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="3f30b-157">Jede Verwendung einer Entität, die als veraltet markiert ist, generiert anschließend eine Warnung oder einen Fehler, je nachdem, wie das Attribut konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="3f30b-157">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="3f30b-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f30b-158">For example:</span></span>

```vb
<System.Obsolete("use class B")>
Class A
    Sub Method()
    End Sub
End Class

Class B
    <System.Obsolete("use NewMethod", True)>
    Sub OldMethod()
    End Sub

    Sub NewMethod()
    End Sub
End Class
```

<span data-ttu-id="3f30b-159">Dieses Beispiel zeigt, wie das `Obsolete`-Attribut auf die `A`-Klasse und die `B.OldMethod`-Methode angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f30b-159">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="3f30b-160">Da das zweite Argument des Attributkonstruktors, das auf `B.OldMethod` angewendet wurde, auf `true` festgelegt wird, verursacht diese Methode einen Compilerfehler. Die Verwendung der `A`-Klasse erzeugt hingegen nur eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="3f30b-160">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="3f30b-161">Wenn Sie `B.NewMethod` aufrufen, werden weder Warnungen noch Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="3f30b-161">Calling `B.NewMethod`, however, produces no warning or error.</span></span>

<span data-ttu-id="3f30b-162">Die Zeichenfolge, die als erstes Argument für den Attributkonstruktor bereitgestellt wurde, wird als Teil der Warnung oder des Fehlers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f30b-162">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="3f30b-163">Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code zwei Warnungen und einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="3f30b-163">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

<span data-ttu-id="3f30b-164">Es werden zwei Warnungen für die Klasse `A` generiert: eine für die Deklaration des Klassenverweises und eine für den Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="3f30b-164">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>

<span data-ttu-id="3f30b-165">Das `Obsolete`-Attribut kann ohne Argumente verwendet werden, jedoch ist das Einschließen einer Erklärung, warum das Element veraltet ist und was demnach verwendet werden soll, empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-165">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>

<span data-ttu-id="3f30b-166">Das `Obsolete`-Attribut ist ein Attribut zur einmaligen Nutzung und kann auf jede Entität angewendet werden, die Attribute zulässt.</span><span class="sxs-lookup"><span data-stu-id="3f30b-166">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="3f30b-167">`Obsolete` ist ein Alias für <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3f30b-167">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

## <a name="conditional-attribute"></a><a name="Conditional"></a><span data-ttu-id="3f30b-168">Conditional-Attribut</span><span class="sxs-lookup"><span data-stu-id="3f30b-168">Conditional Attribute</span></span>

<span data-ttu-id="3f30b-169">Das `Conditional`-Attribut macht die Ausführung einer Methode abhängig von einem Vorverarbeitungsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="3f30b-169">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="3f30b-170">Das `Conditional`-Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute> und kann auf eine Methode oder Attributklasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-170">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="3f30b-171">In diesem Beispiel wird `Conditional` auf eine Methode angewendet, um die Anzeige programmspezifischer Diagnoseinformationen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3f30b-171">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

```vb
#Const TRACE_ON = True
Imports System.Diagnostics

Module TestConditionalAttribute
    Public Class Trace
        <Conditional("TRACE_ON")>
        Public Shared Sub Msg(ByVal msg As String)
            Console.WriteLine(msg)
        End Sub

    End Class

    Sub Main()
        Trace.Msg("Now in Main...")
        Console.WriteLine("Done.")
    End Sub
End Module
```

<span data-ttu-id="3f30b-172">Wenn der `TRACE_ON`-Bezeichner nicht definiert ist, wird keine Ablaufverfolgungsausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3f30b-172">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>

<span data-ttu-id="3f30b-173">Das `Conditional`-Attribut wird oft zusammen mit dem `DEBUG`-Bezeichner verwendet, um die Ablaufverfolgung und Protokollierung von Features zum Debuggen von Builds, jedoch nicht in Releasebuilds, wie folgt zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3f30b-173">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

<span data-ttu-id="3f30b-174">Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder Fehlen des angegebenen Vorverarbeitungssymbols, ob der Aufruf eingeschlossen oder ausgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="3f30b-174">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="3f30b-175">Wenn das Symbol definiert ist, wird der Aufruf einbezogen; andernfalls wird der Aufruf ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-175">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="3f30b-176">Die Verwendung von `Conditional` ist eine sauberere, elegantere und auch weniger fehleranfällige Alternative zum Einschließen von Methoden innerhalb von `#if…#endif`-Blöcken, z.B.:</span><span class="sxs-lookup"><span data-stu-id="3f30b-176">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

<span data-ttu-id="3f30b-177">Eine bedingte Methode muss eine Methode in einer Klassen- oder Stukturdeklaration sein und darf keinen Rückgabewert besitzen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-177">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>

### <a name="using-multiple-identifiers"></a><span data-ttu-id="3f30b-178">Verwenden mehrerer Bezeichner</span><span class="sxs-lookup"><span data-stu-id="3f30b-178">Using Multiple Identifiers</span></span>

<span data-ttu-id="3f30b-179">Wenn eine Methode mehrere `Conditional`-Attribute besitzt, wird ein Aufruf an die Methode eingeschlossen, wenn mindestens eines der bedingten Symbole definiert ist (anders gesagt, sind die Symbole durch Verwendung des OR-Operators logisch miteinander verknüpft).</span><span class="sxs-lookup"><span data-stu-id="3f30b-179">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="3f30b-180">In diesem Beispiel führt das Vorhandensein von `A` oder `B` zu einem Methodenaufruf:</span><span class="sxs-lookup"><span data-stu-id="3f30b-180">In this example, the presence of either `A` or `B` will result in a method call:</span></span>

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

<span data-ttu-id="3f30b-181">Um den Effekt der logischen Verknüpfung von Symbolen durch den AND-Operator zu erzielen, können Sie serielle bedingte Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="3f30b-181">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="3f30b-182">Zum Beispiel wird die zweite Methode unten nur ausgeführt, wenn jeweils `A` und `B` definiert sind:</span><span class="sxs-lookup"><span data-stu-id="3f30b-182">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>

```vb
<Conditional("A")>
Shared Sub DoIfA()
    DoIfAandB()
End Sub

<Conditional("B")>
Shared Sub DoIfAandB()
    ' Code to execute when both A and B are defined...
End Sub
```

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="3f30b-183">Verwenden von Conditional mit Attributklassen</span><span class="sxs-lookup"><span data-stu-id="3f30b-183">Using Conditional with Attribute Classes</span></span>

<span data-ttu-id="3f30b-184">Das `Conditional`-Attribut kann auch auf die Definition einer Attributklasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-184">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="3f30b-185">In diesem Beispiel wird das benutzerdefinierte Attribut `Documentation` den Metadaten nur dann Informationen hinzufügen, wenn DEBUG definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3f30b-185">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>

```vb
<Conditional("DEBUG")>
Public Class Documentation
    Inherits System.Attribute
    Private text As String
    Sub New(ByVal doc_text As String)
        text = doc_text
    End Sub
End Class

Class SampleClass
    ' This attribute will only be included if DEBUG is defined.
    <Documentation("This method displays an integer.")>
    Shared Sub DoWork(ByVal i As Integer)
        System.Console.WriteLine(i)
    End Sub
End Class
```

## <a name="caller-info-attributes"></a><a name="CallerInfo"></a><span data-ttu-id="3f30b-186">Aufruferinfoattribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-186">Caller Info Attributes</span></span>

<span data-ttu-id="3f30b-187">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-187">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="3f30b-188">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-188">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>

<span data-ttu-id="3f30b-189">Um diese Memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-189">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="3f30b-190">Jeder optionale Parameter gibt einen Standardwert an.</span><span class="sxs-lookup"><span data-stu-id="3f30b-190">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="3f30b-191">In der folgenden Tabelle sind die Aufrufer-Informationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace definiert sind:</span><span class="sxs-lookup"><span data-stu-id="3f30b-191">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="3f30b-192">attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-192">Attribute</span></span>|<span data-ttu-id="3f30b-193">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3f30b-193">Description</span></span>|<span data-ttu-id="3f30b-194">Typ</span><span class="sxs-lookup"><span data-stu-id="3f30b-194">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="3f30b-195">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="3f30b-195">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="3f30b-196">Dies ist der Pfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="3f30b-196">This is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="3f30b-197">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird</span><span class="sxs-lookup"><span data-stu-id="3f30b-197">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="3f30b-198">Der Methoden- oder Eigenschaftenname des Aufrufers</span><span class="sxs-lookup"><span data-stu-id="3f30b-198">Method name or property name of the caller.</span></span> <span data-ttu-id="3f30b-199">Weitere Informationen finden Sie unter [Aufruferinformationen (Visual Basic)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="3f30b-199">For more information, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>|`String`|

<span data-ttu-id="3f30b-200">Weitere Informationen zu den aufruferinfoattributen finden Sie unter [Aufruferinformationen (Visual Basic)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="3f30b-200">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>

## <a name="visual-basic-attributes"></a><a name="VB"></a><span data-ttu-id="3f30b-201">Visual Basic Attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-201">Visual Basic Attributes</span></span>

<span data-ttu-id="3f30b-202">In der folgenden Tabelle sind die Attribute aufgeführt, die für Visual Basic spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="3f30b-202">The following table lists the attributes that are specific to Visual Basic.</span></span>

|<span data-ttu-id="3f30b-203">attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-203">Attribute</span></span>|<span data-ttu-id="3f30b-204">Zweck</span><span class="sxs-lookup"><span data-stu-id="3f30b-204">Purpose</span></span>|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|<span data-ttu-id="3f30b-205">Gibt dem Compiler an, dass die Klasse als COM-Objekt verfügbar gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f30b-205">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|<span data-ttu-id="3f30b-206">Ermöglicht den Zugriff auf Modul Elemente mithilfe der Qualifikation, die für das Modul benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="3f30b-206">Allows module members to be accessed using only the qualification needed for the module.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|<span data-ttu-id="3f30b-207">Gibt die Größe einer Zeichenfolge mit fester Länge in einer Struktur zur Verwendung mit Dateieingabe-und Ausgabefunktionen an.</span><span class="sxs-lookup"><span data-stu-id="3f30b-207">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|<span data-ttu-id="3f30b-208">Gibt die Größe eines festgelegten Arrays in einer-Struktur zur Verwendung mit Dateieingabe-und-Ausgabefunktionen an.</span><span class="sxs-lookup"><span data-stu-id="3f30b-208">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|

### <a name="comclassattribute"></a><span data-ttu-id="3f30b-209">ComClassAttribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-209">COMClassAttribute</span></span>

<span data-ttu-id="3f30b-210">Verwenden `COMClassAttribute` Sie, um den Prozess der Erstellung von COM-Komponenten aus Visual Basic zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-210">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="3f30b-211">COM-Objekte unterscheiden sich erheblich von .NET Framework Assemblys, und ohne `COMClassAttribute` müssen Sie eine Reihe von Schritten ausführen, um ein COM-Objekt aus Visual Basic zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3f30b-211">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="3f30b-212">Bei Klassen `COMClassAttribute` , die mit markiert sind, führt der Compiler viele dieser Schritte automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="3f30b-212">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>

### <a name="hidemodulenameattribute"></a><span data-ttu-id="3f30b-213">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-213">HideModuleNameAttribute</span></span>

<span data-ttu-id="3f30b-214">Verwenden `HideModuleNameAttribute` Sie, um den Zugriff auf Modul Elemente nur über die für das Modul erforderliche Qualifikation zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="3f30b-214">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>

### <a name="vbfixedstringattribute"></a><span data-ttu-id="3f30b-215">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-215">VBFixedStringAttribute</span></span>

<span data-ttu-id="3f30b-216">Verwenden `VBFixedStringAttribute` Sie, um Visual Basic zu erzwingen, dass eine Zeichenfolge mit fester Länge erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3f30b-216">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="3f30b-217">Zeichen folgen weisen standardmäßig eine Variable Länge auf, und dieses Attribut ist nützlich, wenn Zeichen folgen in Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-217">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="3f30b-218">Dies veranschaulicht der folgende Code:</span><span class="sxs-lookup"><span data-stu-id="3f30b-218">The following code demonstrates this:</span></span>

```vb
Structure Worker
    ' The runtime uses VBFixedString to determine
    ' if the field should be written out as a fixed size.
    <VBFixedString(10)> Public LastName As String
    <VBFixedString(7)> Public Title As String
    <VBFixedString(2)> Public Rank As String
End Structure
```

### <a name="vbfixedarrayattribute"></a><span data-ttu-id="3f30b-219">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-219">VBFixedArrayAttribute</span></span>

<span data-ttu-id="3f30b-220">Verwenden `VBFixedArrayAttribute` Sie, um Arrays mit fester Größe zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3f30b-220">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="3f30b-221">Wie Visual Basic Zeichen folgen haben Arrays standardmäßig eine Variable Länge.</span><span class="sxs-lookup"><span data-stu-id="3f30b-221">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="3f30b-222">Dieses Attribut ist nützlich, wenn Daten in Dateien serialisiert oder geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3f30b-222">This attribute is useful when serializing or writing data to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f30b-223">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f30b-223">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="3f30b-224">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3f30b-224">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="3f30b-225">Attribute</span><span class="sxs-lookup"><span data-stu-id="3f30b-225">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="3f30b-226">Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f30b-226">Reflection (Visual Basic)</span></span>](../reflection.md)
- <span data-ttu-id="3f30b-227">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="3f30b-227">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)</span></span>

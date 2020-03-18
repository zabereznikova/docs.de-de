---
title: Allgemeine Attribute (C#)
ms.date: 07/20/2015
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
ms.openlocfilehash: 7988dad410c6e51869ec9d7e40d94e874443a5f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398382"
---
# <a name="common-attributes-c"></a><span data-ttu-id="a0ada-102">Allgemeine Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="a0ada-102">Common Attributes (C#)</span></span>
<span data-ttu-id="a0ada-103">Dieses Thema beschreibt die Attribute, die am häufigsten in C#-Programmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-103">This topic describes the attributes that are most commonly used in C# programs.</span></span>  
  
- [<span data-ttu-id="a0ada-104">Globale Attribute</span><span class="sxs-lookup"><span data-stu-id="a0ada-104">Global Attributes</span></span>](#Global)  
  
- [<span data-ttu-id="a0ada-105">Obsolete-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-105">Obsolete Attribute</span></span>](#Obsolete)  
  
- [<span data-ttu-id="a0ada-106">Conditional-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-106">Conditional Attribute</span></span>](#Conditional)  
  
- [<span data-ttu-id="a0ada-107">Aufufrerinfoattribute</span><span class="sxs-lookup"><span data-stu-id="a0ada-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
## <a name="Global"></a> <span data-ttu-id="a0ada-108">Globale Attribute</span><span class="sxs-lookup"><span data-stu-id="a0ada-108">Global Attributes</span></span>  
 <span data-ttu-id="a0ada-109">Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – sie gelten für eine gesamte Assembly oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="a0ada-109">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="a0ada-110">Zum Beispiel kann das <xref:System.Reflection.AssemblyVersionAttribute>-Attribut zum Einbetten von Versionsinformationen in eine Assembly verwendet werden. Diese sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="a0ada-110">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 <span data-ttu-id="a0ada-111">Globale Attribute befinden sich im Quellcode nach allen obersten `using`-Direktiven und vor jeden Typ-, Modul- oder Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-111">Global attributes appear in the source code after any top-level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="a0ada-112">Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierungsdurchlauf kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-112">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="a0ada-113">In C#-Projekten werden globale Attribute in die Datei „AssemblyInfo.cs“ eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a0ada-113">In C# projects, global attributes are put in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="a0ada-114">Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-114">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="a0ada-115">Sie werden in die folgenden Kategorien eingeteilt:</span><span class="sxs-lookup"><span data-stu-id="a0ada-115">They fall into the following categories:</span></span>  
  
- <span data-ttu-id="a0ada-116">Attribute für Assemblyidentitäten</span><span class="sxs-lookup"><span data-stu-id="a0ada-116">Assembly identity attributes</span></span>  
  
- <span data-ttu-id="a0ada-117">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="a0ada-117">Informational attributes</span></span>  
  
- <span data-ttu-id="a0ada-118">Attribute für Assemblymanifeste.</span><span class="sxs-lookup"><span data-stu-id="a0ada-118">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="a0ada-119">Attribute für Assemblyidentitäten</span><span class="sxs-lookup"><span data-stu-id="a0ada-119">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="a0ada-120">Drei Attribute bestimmen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: „name“, „version“ und „culture“.</span><span class="sxs-lookup"><span data-stu-id="a0ada-120">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="a0ada-121">Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf sie verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a0ada-121">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="a0ada-122">Mit Attributen können die Version und Kultur einer Assembly festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-122">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="a0ada-123">Allerdings wird der name-Wert vom Compiler, der Visual Studio-IDE im [Dialogfeld „Assemblyinformationen“](/visualstudio/ide/reference/assembly-information-dialog-box) oder dem Assemblylinker (Al.exe) festgelegt, wenn die Assembly erstellt wird. Die geschieht auf Grundlage der Datei, die das Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="a0ada-123">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="a0ada-124">Das Attribut <xref:System.Reflection.AssemblyFlagsAttribute> gibt an, ob mehrere Kopien der Assembly parallel bestehen können.</span><span class="sxs-lookup"><span data-stu-id="a0ada-124">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="a0ada-125">In der folgenden Tabelle werden die Identitätsattribute aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a0ada-125">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="a0ada-126">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-126">Attribute</span></span>|<span data-ttu-id="a0ada-127">Zweck</span><span class="sxs-lookup"><span data-stu-id="a0ada-127">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="a0ada-128">Beschreibt vollständig die Identität einer Assembly</span><span class="sxs-lookup"><span data-stu-id="a0ada-128">Fully describes the identity of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="a0ada-129">Gibt die Version einer Assembly an</span><span class="sxs-lookup"><span data-stu-id="a0ada-129">Specifies the version of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="a0ada-130">Gibt an, welche Kultur die Assembly unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a0ada-130">Specifies which culture the assembly supports.</span></span>|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="a0ada-131">Gibt an, ob eine Assembly die parallele Ausführung auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt</span><span class="sxs-lookup"><span data-stu-id="a0ada-131">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="a0ada-132">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="a0ada-132">Informational Attributes</span></span>  
 <span data-ttu-id="a0ada-133">Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-133">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="a0ada-134">Die folgende Tabelle zeigt die Informationsattribute, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-134">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="a0ada-135">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-135">Attribute</span></span>|<span data-ttu-id="a0ada-136">Zweck</span><span class="sxs-lookup"><span data-stu-id="a0ada-136">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="a0ada-137">Definiert ein benutzerdefiniertes Attribut, das den Produktnamen für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-137">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="a0ada-138">Definiert ein benutzerdefiniertes Attribut, das eine Marke für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-138">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="a0ada-139">Definiert ein benutzerdefiniertes Attribut, das eine Informationsversion für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-139">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="a0ada-140">Definiert ein benutzerdefiniertes Attribut, das einen Firmennamen für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-140">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="a0ada-141">Definiert ein benutzerdefiniertes Attribut, das ein Copyright für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-141">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="a0ada-142">Weist den Compiler an, eine spezifische Versionsnummer für die Win32-Dateiversionsressource zu verwenden</span><span class="sxs-lookup"><span data-stu-id="a0ada-142">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="a0ada-143">Gibt an, ob die Assembly mit der Common Language Specification (CLS) kompatibel ist</span><span class="sxs-lookup"><span data-stu-id="a0ada-143">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="a0ada-144">Attribute für Assemblymanifeste</span><span class="sxs-lookup"><span data-stu-id="a0ada-144">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="a0ada-145">Sie können Attribute für Assemblymanifeste verwenden, um Informationen im Assemblymanifest bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-145">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="a0ada-146">Dies schließt Titel, Beschreibung, Standardalias und Konfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="a0ada-146">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="a0ada-147">Die folgende Tabelle zeigt die Attribute für Assemblymanifeste, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-147">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="a0ada-148">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-148">Attribute</span></span>|<span data-ttu-id="a0ada-149">Zweck</span><span class="sxs-lookup"><span data-stu-id="a0ada-149">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="a0ada-150">Definiert ein benutzerdefiniertes Attribut, das einen Assemblytitel für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-150">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="a0ada-151">Definiert ein benutzerdefiniertes Attribut, das eine Assemblybeschreibung für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-151">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="a0ada-152">Definiert ein benutzerdefiniertes Attribut, das eine Assemblykonfiguration (z.B. Retail oder Debug) für ein Assemblymanifest angibt</span><span class="sxs-lookup"><span data-stu-id="a0ada-152">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="a0ada-153">Definiert einen benutzerfreundlichen Standardalias für ein Assemblymanifest</span><span class="sxs-lookup"><span data-stu-id="a0ada-153">Defines a friendly default alias for an assembly manifest</span></span>|  
  
## <a name="Obsolete"></a> <span data-ttu-id="a0ada-154">Obsolete-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-154">Obsolete Attribute</span></span>  
 <span data-ttu-id="a0ada-155">Das `Obsolete`-Attribut markiert eine Programmentität als eine, die nicht mehr zur Verwendung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="a0ada-155">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="a0ada-156">Jede Verwendung einer Entität, die als veraltet markiert ist, generiert anschließend eine Warnung oder einen Fehler, je nachdem, wie das Attribut konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a0ada-156">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="a0ada-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a0ada-157">For example:</span></span>  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 <span data-ttu-id="a0ada-158">Dieses Beispiel zeigt, wie das `Obsolete`-Attribut auf die `A`-Klasse und die `B.OldMethod`-Methode angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0ada-158">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="a0ada-159">Da das zweite Argument des Attributkonstruktors, das auf `B.OldMethod` angewendet wurde, auf `true` festgelegt wird, verursacht diese Methode einen Compilerfehler. Die Verwendung der `A`-Klasse erzeugt hingegen nur eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="a0ada-159">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="a0ada-160">Wenn Sie `B.NewMethod` aufrufen, werden weder Warnungen noch Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="a0ada-160">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="a0ada-161">Die Zeichenfolge, die als erstes Argument für den Attributkonstruktor bereitgestellt wurde, wird als Teil der Warnung oder des Fehlers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0ada-161">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="a0ada-162">Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code zwei Warnungen und einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="a0ada-162">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 <span data-ttu-id="a0ada-163">Es werden zwei Warnungen für die Klasse `A` generiert: eine für die Deklaration des Klassenverweises und eine für den Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="a0ada-163">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="a0ada-164">Das `Obsolete`-Attribut kann ohne Argumente verwendet werden, jedoch ist das Einschließen einer Erklärung, warum das Element veraltet ist und was demnach verwendet werden soll, empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-164">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="a0ada-165">Das `Obsolete`-Attribut ist ein Attribut zur einmaligen Nutzung und kann auf jede Entität angewendet werden, die Attribute zulässt.</span><span class="sxs-lookup"><span data-stu-id="a0ada-165">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="a0ada-166">`Obsolete` ist ein Alias für <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a0ada-166">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
## <a name="Conditional"></a> <span data-ttu-id="a0ada-167">Conditional-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-167">Conditional Attribute</span></span>  
 <span data-ttu-id="a0ada-168">Das `Conditional`-Attribut macht die Ausführung einer Methode abhängig von einem Vorverarbeitungsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="a0ada-168">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="a0ada-169">Das `Conditional`-Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute> und kann auf eine Methode oder Attributklasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-169">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="a0ada-170">In diesem Beispiel wird `Conditional` auf eine Methode angewendet, um die Anzeige programmspezifischer Diagnoseinformationen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a0ada-170">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 <span data-ttu-id="a0ada-171">Wenn der `TRACE_ON`-Bezeichner nicht definiert ist, wird keine Ablaufverfolgungsausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0ada-171">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="a0ada-172">Das `Conditional`-Attribut wird oft zusammen mit dem `DEBUG`-Bezeichner verwendet, um die Ablaufverfolgung und Protokollierung von Features zum Debuggen von Builds, jedoch nicht in Releasebuilds, wie folgt zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="a0ada-172">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 <span data-ttu-id="a0ada-173">Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder Fehlen des angegebenen Vorverarbeitungssymbols, ob der Aufruf eingeschlossen oder ausgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="a0ada-173">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="a0ada-174">Wenn das Symbol definiert ist, wird der Aufruf einbezogen; andernfalls wird der Aufruf ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-174">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="a0ada-175">Die Verwendung von `Conditional` ist eine sauberere, elegantere und auch weniger fehleranfällige Alternative zum Einschließen von Methoden innerhalb von `#if…#endif`-Blöcken, z.B.:</span><span class="sxs-lookup"><span data-stu-id="a0ada-175">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 <span data-ttu-id="a0ada-176">Eine bedingte Methode muss eine Methode in einer Klassen- oder Stukturdeklaration sein und darf keinen Rückgabewert besitzen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-176">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="a0ada-177">Verwenden mehrerer Bezeichner</span><span class="sxs-lookup"><span data-stu-id="a0ada-177">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="a0ada-178">Wenn eine Methode mehrere `Conditional`-Attribute besitzt, wird ein Aufruf an die Methode eingeschlossen, wenn mindestens eines der bedingten Symbole definiert ist (anders gesagt, sind die Symbole durch Verwendung des OR-Operators logisch miteinander verknüpft).</span><span class="sxs-lookup"><span data-stu-id="a0ada-178">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="a0ada-179">In diesem Beispiel führt das Vorhandensein von `A` oder `B` zu einem Methodenaufruf:</span><span class="sxs-lookup"><span data-stu-id="a0ada-179">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 <span data-ttu-id="a0ada-180">Um den Effekt der logischen Verknüpfung von Symbolen durch den AND-Operator zu erzielen, können Sie serielle bedingte Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="a0ada-180">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="a0ada-181">Zum Beispiel wird die zweite Methode unten nur ausgeführt, wenn jeweils `A` und `B` definiert sind:</span><span class="sxs-lookup"><span data-stu-id="a0ada-181">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```csharp
[Conditional("A")]  
static void DoIfA()  
{  
    DoIfAandB();  
}  
  
[Conditional("B")]  
static void DoIfAandB()  
{  
    // Code to execute when both A and B are defined...  
}  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="a0ada-182">Verwenden von Conditional mit Attributklassen</span><span class="sxs-lookup"><span data-stu-id="a0ada-182">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="a0ada-183">Das `Conditional`-Attribut kann auch auf die Definition einer Attributklasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-183">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="a0ada-184">In diesem Beispiel wird das benutzerdefinierte Attribut `Documentation` den Metadaten nur dann Informationen hinzufügen, wenn DEBUG definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a0ada-184">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
## <a name="CallerInfo"></a> <span data-ttu-id="a0ada-185">Aufufrerinfoattribute</span><span class="sxs-lookup"><span data-stu-id="a0ada-185">Caller Info Attributes</span></span>  
 <span data-ttu-id="a0ada-186">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-186">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="a0ada-187">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="a0ada-187">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="a0ada-188">Um diese Memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0ada-188">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="a0ada-189">Jeder optionale Parameter gibt einen Standardwert an.</span><span class="sxs-lookup"><span data-stu-id="a0ada-189">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="a0ada-190">In der folgenden Tabelle sind die Aufrufer-Informationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace definiert sind:</span><span class="sxs-lookup"><span data-stu-id="a0ada-190">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="a0ada-191">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ada-191">Attribute</span></span>|<span data-ttu-id="a0ada-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0ada-192">Description</span></span>|<span data-ttu-id="a0ada-193">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a0ada-193">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="a0ada-194">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="a0ada-194">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="a0ada-195">Dies ist der Pfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="a0ada-195">This is the path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="a0ada-196">Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird</span><span class="sxs-lookup"><span data-stu-id="a0ada-196">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="a0ada-197">Der Methoden- oder Eigenschaftenname des Aufrufers</span><span class="sxs-lookup"><span data-stu-id="a0ada-197">Method name or property name of the caller.</span></span> <span data-ttu-id="a0ada-198">Weitere Informationen finden Sie unter [Caller Information (C#) (Aufruferinformationen (C#))](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="a0ada-198">For more information, see [Caller Information (C#)](../caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="a0ada-199">Weitere Informationen zu den Aufruferinformationsattributen finden Sie unter [Caller Information (C#) (Aufruferinformationen (C#))](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="a0ada-199">For more information about the Caller Info attributes, see [Caller Information (C#)](../caller-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ada-200">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0ada-200">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="a0ada-201">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a0ada-201">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="a0ada-202">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0ada-202">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="a0ada-203">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="a0ada-203">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="a0ada-204">Zugriff auf Attribute mit Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="a0ada-204">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)

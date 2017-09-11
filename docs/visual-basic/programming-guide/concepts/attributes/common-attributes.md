---
title: Allgemeine Attribute (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9adb5cb378701c8d06a3fa28bad44dc857026b5a
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="acd25-102">Allgemeine Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acd25-102">Common Attributes (Visual Basic)</span></span>
<span data-ttu-id="acd25-103">Dieses Thema beschreibt die Attribute, die am häufigsten in Visual Basic-Programmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="acd25-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>  
  
-   [<span data-ttu-id="acd25-104">Globale Attribute</span><span class="sxs-lookup"><span data-stu-id="acd25-104">Global Attributes</span></span>](#Global)  
  
-   [<span data-ttu-id="acd25-105">Obsolete-Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-105">Obsolete Attribute</span></span>](#Obsolete)  
  
-   [<span data-ttu-id="acd25-106">Conditional-Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-106">Conditional Attribute</span></span>](#Conditional)  
  
-   [<span data-ttu-id="acd25-107">Aufufrerinfoattribute</span><span class="sxs-lookup"><span data-stu-id="acd25-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
-   [<span data-ttu-id="acd25-108">Visual Basic-Attribute</span><span class="sxs-lookup"><span data-stu-id="acd25-108">Visual Basic Attributes</span></span>](#VB)  
  
##  <span data-ttu-id="acd25-109"><a name="Global"></a>Globale Attribute</span><span class="sxs-lookup"><span data-stu-id="acd25-109"><a name="Global"></a> Global Attributes</span></span>  
 <span data-ttu-id="acd25-110">Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – gelten für eine gesamte Assembly oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="acd25-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="acd25-111">Zum Beispiel die <xref:System.Reflection.AssemblyVersionAttribute>Attribut kann verwendet werden, um Versionsinformationen in eine Assembly wie folgt einzubetten:</xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 <span data-ttu-id="acd25-112">Globale Attribute befinden sich im Quellcode nach allen auf der obersten Ebene`Imports` Anweisungen sowie vor jeder Typ-, Modul- oder Namespace.</span><span class="sxs-lookup"><span data-stu-id="acd25-112">Global attributes appear in the source code after any top-level`Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="acd25-113">Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierung Durchlauf kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="acd25-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="acd25-114">Für Visual Basic-Projekten werden globale Attribute im Allgemeinen in der Datei AssemblyInfo.vb eingefügt (die Datei wird automatisch erstellt, wenn Sie ein Projekt in Visual Studio erstellen).</span><span class="sxs-lookup"><span data-stu-id="acd25-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>  
  
 <span data-ttu-id="acd25-115">Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="acd25-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="acd25-116">Sie können in den folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="acd25-116">They fall into the following categories:</span></span>  
  
-   <span data-ttu-id="acd25-117">Attribute für die Assemblyidentität</span><span class="sxs-lookup"><span data-stu-id="acd25-117">Assembly identity attributes</span></span>  
  
-   <span data-ttu-id="acd25-118">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="acd25-118">Informational attributes</span></span>  
  
-   <span data-ttu-id="acd25-119">Attribute für Assemblymanifeste</span><span class="sxs-lookup"><span data-stu-id="acd25-119">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="acd25-120">Attribute für Assemblyidentitäten</span><span class="sxs-lookup"><span data-stu-id="acd25-120">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="acd25-121">Drei Attribute (mit einem starken Namen, falls zutreffend) bestimmen die Identität einer Assembly: Name, Version und Kultur.</span><span class="sxs-lookup"><span data-stu-id="acd25-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="acd25-122">Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn Sie es im Code verweisen.</span><span class="sxs-lookup"><span data-stu-id="acd25-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="acd25-123">Sie können die Version und Kultur, die unter Verwendung von Attributen einer Assembly festlegen.</span><span class="sxs-lookup"><span data-stu-id="acd25-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="acd25-124">Allerdings wird die Name-Wert festgelegt, durch den Compiler, die Visual Studio-IDE in der [Assembly (Dialogfeld)](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), oder die Assembly Linker (Al.exe) beim Erstellen die Assembly auf Grundlage der Datei, die das Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="acd25-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="acd25-125">Die <xref:System.Reflection.AssemblyFlagsAttribute>Attribut gibt an, ob mehrere Kopien der Assembly vorhanden sein können.</xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="acd25-126">Die folgende Tabelle zeigt die Identitätsattribute.</span><span class="sxs-lookup"><span data-stu-id="acd25-126">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="acd25-127">Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-127">Attribute</span></span>|<span data-ttu-id="acd25-128">Zweck</span><span class="sxs-lookup"><span data-stu-id="acd25-128">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="acd25-129"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="acd25-129"><xref:System.Reflection.AssemblyName></span></span>|<span data-ttu-id="acd25-130">Vollständige Beschreibung der Identität einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="acd25-130">Fully describes the identity of an assembly.</span></span>|  
|<span data-ttu-id="acd25-131"><xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-131"><xref:System.Reflection.AssemblyVersionAttribute></span></span>|<span data-ttu-id="acd25-132">Gibt die Version einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="acd25-132">Specifies the version of an assembly.</span></span>|  
|<span data-ttu-id="acd25-133"><xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-133"><xref:System.Reflection.AssemblyCultureAttribute></span></span>|<span data-ttu-id="acd25-134">Gibt an, welche Kultur die Assembly unterstützt.</span><span class="sxs-lookup"><span data-stu-id="acd25-134">Specifies which culture the assembly supports.</span></span>|  
|<span data-ttu-id="acd25-135"><xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-135"><xref:System.Reflection.AssemblyFlagsAttribute></span></span>|<span data-ttu-id="acd25-136">Gibt an, ob eine Assembly Side-by-Side Execution auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt.</span><span class="sxs-lookup"><span data-stu-id="acd25-136">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="acd25-137">Informationsattribute</span><span class="sxs-lookup"><span data-stu-id="acd25-137">Informational Attributes</span></span>  
 <span data-ttu-id="acd25-138">Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="acd25-138">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="acd25-139">In der folgenden Tabelle sind die Informationsattribute gemäß der <xref:System.Reflection?displayProperty=fullName>Namespace.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="acd25-139">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="acd25-140">Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-140">Attribute</span></span>|<span data-ttu-id="acd25-141">Zweck</span><span class="sxs-lookup"><span data-stu-id="acd25-141">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="acd25-142"><xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-142"><xref:System.Reflection.AssemblyProductAttribute></span></span>|<span data-ttu-id="acd25-143">Definiert ein benutzerdefiniertes Attribut, das einen Produktnamen für ein Assemblymanifest angibt.</span><span class="sxs-lookup"><span data-stu-id="acd25-143">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-144"><xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-144"><xref:System.Reflection.AssemblyTrademarkAttribute></span></span>|<span data-ttu-id="acd25-145">Definiert ein benutzerdefiniertes Attribut, das eine Marke für ein Assemblymanifest angibt.</span><span class="sxs-lookup"><span data-stu-id="acd25-145">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></span></span>|<span data-ttu-id="acd25-147">Definiert ein benutzerdefiniertes Attribut, das eine Informationsversion für ein Assemblymanifest angibt.</span><span class="sxs-lookup"><span data-stu-id="acd25-147">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-148"><xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-148"><xref:System.Reflection.AssemblyCompanyAttribute></span></span>|<span data-ttu-id="acd25-149">Definiert ein benutzerdefiniertes Attribut, das einen Firmennamen für ein Assemblymanifest angibt.</span><span class="sxs-lookup"><span data-stu-id="acd25-149">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-150"><xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-150"><xref:System.Reflection.AssemblyCopyrightAttribute></span></span>|<span data-ttu-id="acd25-151">Definiert ein benutzerdefiniertes Attribut, das ein Copyright für ein Assemblymanifest angibt.</span><span class="sxs-lookup"><span data-stu-id="acd25-151">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-152"><xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-152"><xref:System.Reflection.AssemblyFileVersionAttribute></span></span>|<span data-ttu-id="acd25-153">Weist den Compiler an, eine bestimmte Versionsnummer für die Win32-Versionsressource verwenden.</span><span class="sxs-lookup"><span data-stu-id="acd25-153">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<span data-ttu-id="acd25-154"><xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-154"><xref:System.CLSCompliantAttribute></span></span>|<span data-ttu-id="acd25-155">Gibt an, ob die Assembly mit der Common Language Specification (CLS) kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="acd25-155">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="acd25-156">Attribute für Assemblymanifeste</span><span class="sxs-lookup"><span data-stu-id="acd25-156">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="acd25-157">Attribute für Assemblymanifeste können Sie Informationen im Assemblymanifest bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="acd25-157">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="acd25-158">Dies schließt Titel, Beschreibung, Standardalias und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="acd25-158">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="acd25-159">Die folgende Tabelle zeigt die Attribute für Assemblymanifeste gemäß der <xref:System.Reflection?displayProperty=fullName>Namespace.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="acd25-159">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="acd25-160">Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-160">Attribute</span></span>|<span data-ttu-id="acd25-161">Zweck</span><span class="sxs-lookup"><span data-stu-id="acd25-161">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="acd25-162"><xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-162"><xref:System.Reflection.AssemblyTitleAttribute></span></span>|<span data-ttu-id="acd25-163">Definiert ein benutzerdefiniertes Attribut, das einen Assemblytitel für ein Assemblymanifest angibt.</span><span class="sxs-lookup"><span data-stu-id="acd25-163">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-164"><xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-164"><xref:System.Reflection.AssemblyDescriptionAttribute></span></span>|<span data-ttu-id="acd25-165">Definiert ein benutzerdefiniertes Attribut, das eine Assemblybeschreibung für ein Assemblymanifest angibt.</span><span class="sxs-lookup"><span data-stu-id="acd25-165">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-166"><xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-166"><xref:System.Reflection.AssemblyConfigurationAttribute></span></span>|<span data-ttu-id="acd25-167">Definiert ein benutzerdefiniertes Attribut, das eine Assemblykonfiguration (z. B. Verkaufs- oder Debugversion) für ein Assemblymanifest.</span><span class="sxs-lookup"><span data-stu-id="acd25-167">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<span data-ttu-id="acd25-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></span></span>|<span data-ttu-id="acd25-169">Definiert einen langen Standardalias für ein Assemblymanifest.</span><span class="sxs-lookup"><span data-stu-id="acd25-169">Defines a friendly default alias for an assembly manifest</span></span>|  
  
##  <span data-ttu-id="acd25-170"><a name="Obsolete"></a>Obsolete-Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-170"><a name="Obsolete"></a> Obsolete Attribute</span></span>  
 <span data-ttu-id="acd25-171">Das `Obsolete` -Attribut markiert eine Programmentität als eine, die nicht mehr zur Verwendung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="acd25-171">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="acd25-172">Jede Verwendung einer Entität, die als veraltet markiert generiert eine Warnung oder ein Fehler auftritt, je nachdem, wie das Attribut konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="acd25-172">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="acd25-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="acd25-173">For example:</span></span>  
  
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
  
 <span data-ttu-id="acd25-174">In diesem Beispiel wird die `Obsolete` -Attribut auf die Klasse angewendet wird `A` und Methode `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="acd25-174">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="acd25-175">Da das zweite Argument des Attributkonstruktors zugewiesen `B.OldMethod` auf festgelegt ist `true`, diese Methode verursacht einen Compilerfehler, Verwendung `A` wird nur generieren eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="acd25-175">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="acd25-176">Aufrufen von `B.NewMethod`, generiert jedoch keine Warnung oder Fehler.</span><span class="sxs-lookup"><span data-stu-id="acd25-176">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="acd25-177">Als erstes Argument an den Attributkonstruktor bereitgestellte Zeichenfolge wird als Teil der Warnung oder Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="acd25-177">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="acd25-178">Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code z. B. zwei Warnungen und einen Fehler:</span><span class="sxs-lookup"><span data-stu-id="acd25-178">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 <span data-ttu-id="acd25-179">Zwei Warnungen für Klasse `A` generiert werden: eine für die Deklaration der Klassenreferenz und eine für den Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="acd25-179">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="acd25-180">Das `Obsolete` -Attribut kann ohne Argumente verwendet werden, aber einschließlich der Grund, warum das Element ist veraltet und was verwenden sollte.</span><span class="sxs-lookup"><span data-stu-id="acd25-180">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="acd25-181">Das `Obsolete` -Attribut ist ein Attribut und kann auf jede Entität, die Attribute kann angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="acd25-181">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="acd25-182">`Obsolete`ist ein Alias für <xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-182">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
##  <span data-ttu-id="acd25-183"><a name="Conditional"></a>Conditional-Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-183"><a name="Conditional"></a> Conditional Attribute</span></span>  
 <span data-ttu-id="acd25-184">Die `Conditional` Attribut macht die Ausführung einer Methode eine Präprozessorbezeichner abhängig.</span><span class="sxs-lookup"><span data-stu-id="acd25-184">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="acd25-185">Die `Conditional` -Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute>, und kann auf eine Methode oder ein Attribut-Klasse angewendet werden</xref:System.Diagnostics.ConditionalAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-185">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="acd25-186">In diesem Beispiel `Conditional` auf eine Methode zum Aktivieren oder Deaktivieren der Anzeige von Diagnoseinformationen programmspezifische angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="acd25-186">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```vb  
#Const TRACE_ON = True  
Imports System  
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
  
 <span data-ttu-id="acd25-187">Wenn die `TRACE_ON` Bezeichner nicht definiert ist, wird keine Ablaufverfolgungsausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="acd25-187">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="acd25-188">Die `Conditional` Attribut wird häufig zusammen mit der `DEBUG` folgendermaßen Bezeichner Trace und Features für Debugbuilds jedoch nicht in Releasebuilds für die Protokollierung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="acd25-188">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 <span data-ttu-id="acd25-189">Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder fehlen von der angegebenen Vorverarbeitungssymbol, ob der Aufruf eingeschlossen oder ausgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="acd25-189">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="acd25-190">Wenn das Symbol definiert ist, wird der Aufruf einbezogen; Andernfalls wird der Aufruf ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="acd25-190">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="acd25-191">Mithilfe von `Conditional` ist eine sauberere elegantere und weniger fehleranfällige Alternative zum Einschließen von Methoden in `#if…#endif` Blöcken, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="acd25-191">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 <span data-ttu-id="acd25-192">Eine bedingte Methode muss eine Methode in der Deklaration einer Klasse oder Struktur sein und dürfen keinen Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="acd25-192">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="acd25-193">Verwenden mehrerer Bezeichner</span><span class="sxs-lookup"><span data-stu-id="acd25-193">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="acd25-194">Wenn eine Methode mehrere `Conditional` Attribute, ein Aufruf der Methode ist enthalten, wenn mindestens eines der Symbole für bedingte definiert ist (das heißt, die Symbole logisch miteinander verknüpft sind mit dem OR-Operator).</span><span class="sxs-lookup"><span data-stu-id="acd25-194">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="acd25-195">In diesem Beispiel ist das Vorhandensein von `A` oder `B` führt zu einem Methodenaufruf:</span><span class="sxs-lookup"><span data-stu-id="acd25-195">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 <span data-ttu-id="acd25-196">Symbole mit dem AND-Operator logisch zu verbinden Effekt zu erzielen, können Sie bedingte Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="acd25-196">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="acd25-197">Angenommen, die nachfolgende zweite Methode nur ausgeführt, wenn beide `A` und `B` sind definiert:</span><span class="sxs-lookup"><span data-stu-id="acd25-197">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
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
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="acd25-198">Verwenden von Conditional für Attributklassen</span><span class="sxs-lookup"><span data-stu-id="acd25-198">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="acd25-199">Die `Conditional` Attribut kann auch auf die Definition einer Attributklasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="acd25-199">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="acd25-200">In diesem Beispiel wird das benutzerdefinierte Attribut `Documentation` wird nur auf die Metadaten Informationen hinzufügen, wenn DEBUG definiert ist.</span><span class="sxs-lookup"><span data-stu-id="acd25-200">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
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
  
##  <span data-ttu-id="acd25-201"><a name="CallerInfo"></a>Aufufrerinfoattribute</span><span class="sxs-lookup"><span data-stu-id="acd25-201"><a name="CallerInfo"></a> Caller Info Attributes</span></span>  
 <span data-ttu-id="acd25-202">Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="acd25-202">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="acd25-203">Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.</span><span class="sxs-lookup"><span data-stu-id="acd25-203">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="acd25-204">Um memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="acd25-204">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="acd25-205">Jeder Optionaler Parameter gibt den Standardwert an.</span><span class="sxs-lookup"><span data-stu-id="acd25-205">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="acd25-206">Die folgende Tabelle enthält die Aufrufer-Informationsattribute angegeben, die in definiert sind die <xref:System.Runtime.CompilerServices?displayProperty=fullName>Namespace:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="acd25-206">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="acd25-207">Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-207">Attribute</span></span>|<span data-ttu-id="acd25-208">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acd25-208">Description</span></span>|<span data-ttu-id="acd25-209">Typ</span><span class="sxs-lookup"><span data-stu-id="acd25-209">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="acd25-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="acd25-211">Vollständiger Pfad der Quelldatei, die den Aufrufer enthält.</span><span class="sxs-lookup"><span data-stu-id="acd25-211">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="acd25-212">Dies ist der Pfad zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="acd25-212">This is the path at compile time.</span></span>|`String`|  
|<span data-ttu-id="acd25-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="acd25-214">Die Zeilennummer in der Quelldatei, von der die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="acd25-214">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="acd25-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="acd25-216">Name der Methode oder Eigenschaft des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="acd25-216">Method name or property name of the caller.</span></span> <span data-ttu-id="acd25-217">Weitere Informationen finden Sie unter [Aufruferinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="acd25-217">For more information, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="acd25-218">Weitere Informationen zu den Aufrufer-Informationsattribute, finden Sie unter [Aufruferinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="acd25-218">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
##  <span data-ttu-id="acd25-219"><a name="VB"></a>Visual Basic-Attribute</span><span class="sxs-lookup"><span data-stu-id="acd25-219"><a name="VB"></a> Visual Basic Attributes</span></span>  
 <span data-ttu-id="acd25-220">Die folgende Tabelle enthält die Attribute, die für Visual Basic spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="acd25-220">The following table lists the attributes that are specific to Visual Basic.</span></span>  
  
|<span data-ttu-id="acd25-221">Attribut</span><span class="sxs-lookup"><span data-stu-id="acd25-221">Attribute</span></span>|<span data-ttu-id="acd25-222">Zweck</span><span class="sxs-lookup"><span data-stu-id="acd25-222">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="acd25-223"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-223"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>|<span data-ttu-id="acd25-224">Weist den Compiler an, dass die Klasse als COM-Objekt verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acd25-224">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|  
|<span data-ttu-id="acd25-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></span></span>|<span data-ttu-id="acd25-226">Ermöglicht nur die Zugriffsberechtigungen für das Modul benötigt zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="acd25-226">Allows module members to be accessed using only the qualification needed for the module.</span></span>|  
|<span data-ttu-id="acd25-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></span></span>|<span data-ttu-id="acd25-228">Gibt die Größe einer Zeichenfolge fester Länge in einer Struktur für die Verwendung mit Datei-Eingabe und Ausgabe Funktionen.</span><span class="sxs-lookup"><span data-stu-id="acd25-228">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|  
|<span data-ttu-id="acd25-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span><span class="sxs-lookup"><span data-stu-id="acd25-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span></span>|<span data-ttu-id="acd25-230">Gibt die Größe eines festen Arrays in einer Struktur für die Verwendung mit Datei-Eingabe und Ausgabe Funktionen.</span><span class="sxs-lookup"><span data-stu-id="acd25-230">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|  
  
### <a name="comclassattribute"></a><span data-ttu-id="acd25-231">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="acd25-231">COMClassAttribute</span></span>  
 <span data-ttu-id="acd25-232">Verwendung `COMClassAttribute` vereinfacht das Erstellen von COM-Komponenten aus Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="acd25-232">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="acd25-233">COM-Objekte unterscheiden sich erheblich von .NET Framework-Assemblys und ohne `COMClassAttribute`, müssen Sie eine Reihe von Schritten, um ein COM-Objekt in Visual Basic zu generieren.</span><span class="sxs-lookup"><span data-stu-id="acd25-233">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="acd25-234">Für Klassen mit `COMClassAttribute`, der Compiler viele dieser Schritte automatisch durchführt.</span><span class="sxs-lookup"><span data-stu-id="acd25-234">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>  
  
### <a name="hidemodulenameattribute"></a><span data-ttu-id="acd25-235">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="acd25-235">HideModuleNameAttribute</span></span>  
 <span data-ttu-id="acd25-236">Verwendung `HideModuleNameAttribute` auf die Member des Moduls nur die Zugriffsberechtigungen für das Modul benötigt zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="acd25-236">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>  
  
### <a name="vbfixedstringattribute"></a><span data-ttu-id="acd25-237">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="acd25-237">VBFixedStringAttribute</span></span>  
 <span data-ttu-id="acd25-238">Verwendung `VBFixedStringAttribute` zu erzwingen, dass Visual Basic zum Erstellen einer Zeichenfolge fester Länge.</span><span class="sxs-lookup"><span data-stu-id="acd25-238">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="acd25-239">Zeichenfolgen mit variabler Länge in der Standardeinstellung sind, und dieses Attribut ist hilfreich, wenn Sie Zeichenfolgen in Dateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="acd25-239">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="acd25-240">Der folgende Code veranschaulicht dies:</span><span class="sxs-lookup"><span data-stu-id="acd25-240">The following code demonstrates this:</span></span>  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a><span data-ttu-id="acd25-241">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="acd25-241">VBFixedArrayAttribute</span></span>  
 <span data-ttu-id="acd25-242">Verwendung `VBFixedArrayAttribute` Arrays deklarieren, die eine feste Größe sind.</span><span class="sxs-lookup"><span data-stu-id="acd25-242">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="acd25-243">Ähnlich wie Zeichenfolgen in Visual Basic haben Arrays standardmäßig eine Variable Länge.</span><span class="sxs-lookup"><span data-stu-id="acd25-243">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="acd25-244">Dieses Attribut ist hilfreich bei der Serialisierung oder Schreiben von Daten in Dateien.</span><span class="sxs-lookup"><span data-stu-id="acd25-244">This attribute is useful when serializing or writing data to files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd25-245">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acd25-245">See Also</span></span>  
 <span data-ttu-id="acd25-246"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="acd25-246"><xref:System.Reflection></span></span>   
 <span data-ttu-id="acd25-247"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="acd25-247"><xref:System.Attribute></span></span>   
<span data-ttu-id="acd25-248"> [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="acd25-248"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="acd25-249"> [Attribute](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="acd25-249"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="acd25-250"> [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="acd25-250"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="acd25-251"> [Zugriff auf Attribute mit Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="acd25-251"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>

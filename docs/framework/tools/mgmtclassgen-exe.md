---
title: Mgmtclassgen.exe (Management Strongly Typed Class Generator)
description: Lernen Sie „Mgmtclassgen.exe“ kennen, den Generator für stark typisierte Verwaltungsklassen. Mit diesem Tool können Sie schnell eine früh gebundene verwaltete Klasse für eine WMI-Klasse generieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CIM types
- Management Strongly Typed Class Generator
- WMI class
- Mgmtclassgen.exe
- early-bound managed classes
ms.assetid: 02ce6699-49b5-4a0b-b0d5-1003c491232e
ms.openlocfilehash: 89facd4369dad6168e46febd3e34d7f7c235faf0
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517294"
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a><span data-ttu-id="6b118-104">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span><span class="sxs-lookup"><span data-stu-id="6b118-104">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>
<span data-ttu-id="6b118-105">Mit dem Management Strongly Typed Class Generator-Tool können Sie schnell eine früh gebundene Klasse für eine angegebene WMI (Windows Management Instrumentation)-Klasse generieren.</span><span class="sxs-lookup"><span data-stu-id="6b118-105">The Management Strongly Typed Class Generator tool enables you to quickly generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span> <span data-ttu-id="6b118-106">Die generierte Klasse vereinfacht den Code, den Sie für den Zugriff auf eine Instanz der WMI-Klasse schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="6b118-106">The generated class simplifies the code you must write to access an instance of the WMI class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b118-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b118-107">Syntax</span></span>  
  
```console  
mgmtclassgen
WMIClass [options]
```  
  
|<span data-ttu-id="6b118-108">Argument</span><span class="sxs-lookup"><span data-stu-id="6b118-108">Argument</span></span>|<span data-ttu-id="6b118-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b118-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6b118-110">*WMIClass*</span><span class="sxs-lookup"><span data-stu-id="6b118-110">*WMIClass*</span></span>|<span data-ttu-id="6b118-111">Die WMI (Windows Management Instrumentation)-Klasse, für die eine früh gebundene verwaltete Klasse generiert wird.</span><span class="sxs-lookup"><span data-stu-id="6b118-111">The Windows Management Instrumentation class for which to generate an early-bound managed class.</span></span>|  
  
|<span data-ttu-id="6b118-112">Option</span><span class="sxs-lookup"><span data-stu-id="6b118-112">Option</span></span>|<span data-ttu-id="6b118-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b118-113">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6b118-114">**/l**  *language*</span><span class="sxs-lookup"><span data-stu-id="6b118-114">**/l**  *language*</span></span>|<span data-ttu-id="6b118-115">Gibt die Programmiersprache an, in der die früh gebundene verwaltete Klasse generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b118-115">Specifies the language in which to generate the early-bound managed class.</span></span> <span data-ttu-id="6b118-116">Als Sprachargument können Sie **CS** (C#, Standard), **VB** (Visual Basic), **MC** (C++) oder **JS** (JScript) festlegen.</span><span class="sxs-lookup"><span data-stu-id="6b118-116">You can specify **CS** (C#; default), **VB** (Visual Basic),  **MC** (C++), or **JS** (JScript) as the language argument.</span></span>|  
|<span data-ttu-id="6b118-117">**/m**  *machine*</span><span class="sxs-lookup"><span data-stu-id="6b118-117">**/m**  *machine*</span></span>|<span data-ttu-id="6b118-118">Gibt den Computer an, auf dem sich die WMI-Klasse befindet und mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b118-118">Specifies the computer to connect to, where the WMI class resides.</span></span> <span data-ttu-id="6b118-119">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="6b118-119">The default is the local computer.</span></span>|  
|<span data-ttu-id="6b118-120">**/n**  *path*</span><span class="sxs-lookup"><span data-stu-id="6b118-120">**/n**  *path*</span></span>|<span data-ttu-id="6b118-121">Gibt den Pfad zum WMI-Namespace an, der die WMI-Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="6b118-121">Specifies the path to the WMI namespace that contains the WMI class.</span></span> <span data-ttu-id="6b118-122">Wenn Sie keinen Pfad angeben, generiert das Tool den Code für *WMIClass* im Namespace **Root\cimv2-Standard**.</span><span class="sxs-lookup"><span data-stu-id="6b118-122">If you do not specify this option, the tool generates code for *WMIClass* in the default **Root\cimv2** namespace.</span></span>|  
|<span data-ttu-id="6b118-123">**/o**  *classnamespace*</span><span class="sxs-lookup"><span data-stu-id="6b118-123">**/o**  *classnamespace*</span></span>|<span data-ttu-id="6b118-124">Gibt den .NET-Namespace an, in dem die verwaltete Codeklasse generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b118-124">Specifies the .NET namespace in which to generate the managed code class.</span></span> <span data-ttu-id="6b118-125">Wenn Sie keinen Klassennamespace angeben, generiert das Tool den Namespace aus dem WMI-Namespace und dem Schemapräfix.</span><span class="sxs-lookup"><span data-stu-id="6b118-125">If you do not specify this option, the tool generates the namespace using the WMI namespace and the schema prefix.</span></span> <span data-ttu-id="6b118-126">Das Schemapräfix ist der Bestandteil des Klassennamens, der dem Unterstrich vorangeht.</span><span class="sxs-lookup"><span data-stu-id="6b118-126">The schema prefix is the part of the class name preceding the underscore character.</span></span> <span data-ttu-id="6b118-127">Für die **Win32_OperatingSystem**-Klasse im **Root\cimv2**-Namespace würde die Klasse beispielsweise in **ROOT.CIMV2.Win32** generiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b118-127">For example, for the **Win32_OperatingSystem** class in the **Root\cimv2** namespace, the tool would generate the class in **ROOT.CIMV2.Win32**.</span></span>|  
|<span data-ttu-id="6b118-128">**/p**  *filepath*</span><span class="sxs-lookup"><span data-stu-id="6b118-128">**/p**  *filepath*</span></span>|<span data-ttu-id="6b118-129">Gibt den Pfad zur Datei an, in der der generierte Code gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b118-129">Specifies the path to the file in which to save the generated code.</span></span> <span data-ttu-id="6b118-130">Wenn Sie keinen Dateipfad angeben, erstellt das Tool die Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6b118-130">If you do not specify this option, the tool creates the file in the current directory.</span></span> <span data-ttu-id="6b118-131">Es benennt die Klasse und die Datei, in der diese erstellt wird, anhand des *WMIClass*-Arguments.</span><span class="sxs-lookup"><span data-stu-id="6b118-131">It names the class and file in which it generates the class using the *WMIClass* argument.</span></span> <span data-ttu-id="6b118-132">Die Namen der Klasse und der Datei stimmen mit dem Namen der *WMIClass* überein.</span><span class="sxs-lookup"><span data-stu-id="6b118-132">The name of the class and the file are the same as the name of the *WMIClass.*</span></span> <span data-ttu-id="6b118-133">Wenn *WMIClass* einen Unterstrich enthält, wird der Teil des Namens nach dem Unterstrich verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b118-133">If *WMIClass* contains an underscore character, the tool uses the part of the class name following the underscore character.</span></span> <span data-ttu-id="6b118-134">Wenn etwa der *WMIClass*-Name das Format **Win32_LogicalDisk** aufweist, werden die generierte Klasse und Datei mit „logicaldisk“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6b118-134">For example, if the *WMIClass* name is in the format **Win32_LogicalDisk**, the generated class and file is named "logicaldisk".</span></span> <span data-ttu-id="6b118-135">Wenn bereits eine gleichnamige Datei vorhanden ist, wird diese überschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b118-135">If a file already exists, the tool overwrites the existing file.</span></span>|  
|<span data-ttu-id="6b118-136">**/pw**  *password*</span><span class="sxs-lookup"><span data-stu-id="6b118-136">**/pw**  *password*</span></span>|<span data-ttu-id="6b118-137">Gibt das Kennwort für die Anmeldung an einem Computer an, der durch die **/m**-Option angegeben ist</span><span class="sxs-lookup"><span data-stu-id="6b118-137">Specifies the password to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="6b118-138">**/u**  *user name*</span><span class="sxs-lookup"><span data-stu-id="6b118-138">**/u**  *user name*</span></span>|<span data-ttu-id="6b118-139">Gibt den Benutzernamen für die Anmeldung an einem Computer an, der durch die **/m**-Option angegeben ist</span><span class="sxs-lookup"><span data-stu-id="6b118-139">Specifies the user name to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="6b118-140">**/?**</span><span class="sxs-lookup"><span data-stu-id="6b118-140">**/?**</span></span>|<span data-ttu-id="6b118-141">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="6b118-141">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b118-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b118-142">Remarks</span></span>  
 <span data-ttu-id="6b118-143">"Mgmtclassgen.exe" verwendet die <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="6b118-143">Mgmtclassgen.exe uses the <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6b118-144">Sie können daher mit einem beliebigen benutzerdefinierten Codeanbieter Code in anderen verwalteten Sprachen als C#, Visual Basic und JScript generieren.</span><span class="sxs-lookup"><span data-stu-id="6b118-144">Therefore, you can use any custom code provider to generate code in managed languages other than C#, Visual Basic, and JScript.</span></span>  
  
 <span data-ttu-id="6b118-145">Beachten Sie, dass die generierten Klassen an das Schema gebunden sind, für das sie generiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b118-145">Note that generated classes are bound to the schema for which they are generated.</span></span> <span data-ttu-id="6b118-146">Änderungen am zugrunde liegenden Schema wirken sich auf die Klasse erst nach einer Neugenerierung aus.</span><span class="sxs-lookup"><span data-stu-id="6b118-146">If the underlying schema changes, you must regenerate the class if you want it to reflect changes to the schema.</span></span>  
  
 <span data-ttu-id="6b118-147">In der folgenden Tabelle wird die Zuordnung von WMI Common Information Model (CIM)-Typen zu Datentypen in einer generierten Klasse dargestellt:</span><span class="sxs-lookup"><span data-stu-id="6b118-147">The following table shows how WMI Common Information Model (CIM) types map to data types in a generated class:</span></span>  
  
|<span data-ttu-id="6b118-148">CIM-Typ</span><span class="sxs-lookup"><span data-stu-id="6b118-148">CIM type</span></span>|<span data-ttu-id="6b118-149">Datentyp in der generierten Klasse</span><span class="sxs-lookup"><span data-stu-id="6b118-149">Data type in the generated class</span></span>|  
|--------------|--------------------------------------|  
|<span data-ttu-id="6b118-150">CIM_SINT8</span><span class="sxs-lookup"><span data-stu-id="6b118-150">CIM_SINT8</span></span>|<span data-ttu-id="6b118-151">**SByte**</span><span class="sxs-lookup"><span data-stu-id="6b118-151">**SByte**</span></span>|  
|<span data-ttu-id="6b118-152">CIM_UINT8</span><span class="sxs-lookup"><span data-stu-id="6b118-152">CIM_UINT8</span></span>|<span data-ttu-id="6b118-153">**Byte**</span><span class="sxs-lookup"><span data-stu-id="6b118-153">**Byte**</span></span>|  
|<span data-ttu-id="6b118-154">CIM_SINT16</span><span class="sxs-lookup"><span data-stu-id="6b118-154">CIM_SINT16</span></span>|<span data-ttu-id="6b118-155">**Int16**</span><span class="sxs-lookup"><span data-stu-id="6b118-155">**Int16**</span></span>|  
|<span data-ttu-id="6b118-156">CIM_UINT16</span><span class="sxs-lookup"><span data-stu-id="6b118-156">CIM_UINT16</span></span>|<span data-ttu-id="6b118-157">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="6b118-157">**UInt16**</span></span>|  
|<span data-ttu-id="6b118-158">CIM_SINT32</span><span class="sxs-lookup"><span data-stu-id="6b118-158">CIM_SINT32</span></span>|<span data-ttu-id="6b118-159">**Int32**</span><span class="sxs-lookup"><span data-stu-id="6b118-159">**Int32**</span></span>|  
|<span data-ttu-id="6b118-160">SIM_UINT32</span><span class="sxs-lookup"><span data-stu-id="6b118-160">SIM_UINT32</span></span>|<span data-ttu-id="6b118-161">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="6b118-161">**UInt32**</span></span>|  
|<span data-ttu-id="6b118-162">CIM_SINT64</span><span class="sxs-lookup"><span data-stu-id="6b118-162">CIM_SINT64</span></span>|<span data-ttu-id="6b118-163">**Int64**</span><span class="sxs-lookup"><span data-stu-id="6b118-163">**Int64**</span></span>|  
|<span data-ttu-id="6b118-164">CIM_UINT64</span><span class="sxs-lookup"><span data-stu-id="6b118-164">CIM_UINT64</span></span>|<span data-ttu-id="6b118-165">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="6b118-165">**UInt64**</span></span>|  
|<span data-ttu-id="6b118-166">CIM_REAL32</span><span class="sxs-lookup"><span data-stu-id="6b118-166">CIM_REAL32</span></span>|<span data-ttu-id="6b118-167">**Single**</span><span class="sxs-lookup"><span data-stu-id="6b118-167">**Single**</span></span>|  
|<span data-ttu-id="6b118-168">CIM_REAL64</span><span class="sxs-lookup"><span data-stu-id="6b118-168">CIM_REAL64</span></span>|<span data-ttu-id="6b118-169">**Double**</span><span class="sxs-lookup"><span data-stu-id="6b118-169">**Double**</span></span>|  
|<span data-ttu-id="6b118-170">CIM_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6b118-170">CIM_BOOLEAN</span></span>|<span data-ttu-id="6b118-171">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="6b118-171">**Boolean**</span></span>|  
|<span data-ttu-id="6b118-172">CIM_String</span><span class="sxs-lookup"><span data-stu-id="6b118-172">CIM_String</span></span>|<span data-ttu-id="6b118-173">**String**</span><span class="sxs-lookup"><span data-stu-id="6b118-173">**String**</span></span>|  
|<span data-ttu-id="6b118-174">CIM_DATETIME</span><span class="sxs-lookup"><span data-stu-id="6b118-174">CIM_DATETIME</span></span>|<span data-ttu-id="6b118-175">**DateTime** oder **TimeSpan**</span><span class="sxs-lookup"><span data-stu-id="6b118-175">**DateTime** or **TimeSpan**</span></span>|  
|<span data-ttu-id="6b118-176">CIM_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="6b118-176">CIM_REFERENCE</span></span>|<span data-ttu-id="6b118-177">**ManagementPath**</span><span class="sxs-lookup"><span data-stu-id="6b118-177">**ManagementPath**</span></span>|  
|<span data-ttu-id="6b118-178">CIM_CHAR16</span><span class="sxs-lookup"><span data-stu-id="6b118-178">CIM_CHAR16</span></span>|<span data-ttu-id="6b118-179">**Char**</span><span class="sxs-lookup"><span data-stu-id="6b118-179">**Char**</span></span>|  
|<span data-ttu-id="6b118-180">CIM_OBJECT</span><span class="sxs-lookup"><span data-stu-id="6b118-180">CIM_OBJECT</span></span>|<span data-ttu-id="6b118-181">**ManagementBaseObject**</span><span class="sxs-lookup"><span data-stu-id="6b118-181">**ManagementBaseObject**</span></span>|  
|<span data-ttu-id="6b118-182">CIM_IUNKNOWN</span><span class="sxs-lookup"><span data-stu-id="6b118-182">CIM_IUNKNOWN</span></span>|<span data-ttu-id="6b118-183">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="6b118-183">**Object**</span></span>|  
|<span data-ttu-id="6b118-184">CIM_ARRAY</span><span class="sxs-lookup"><span data-stu-id="6b118-184">CIM_ARRAY</span></span>|<span data-ttu-id="6b118-185">Array der zuvor aufgeführten Objekte</span><span class="sxs-lookup"><span data-stu-id="6b118-185">Array of the above mentioned objects</span></span>|  
  
 <span data-ttu-id="6b118-186">Beim Generieren einer WMI-Klasse werden Sie folgende Verhaltensweisen feststellen:</span><span class="sxs-lookup"><span data-stu-id="6b118-186">Note the following behaviors when you generate a WMI class:</span></span>  
  
- <span data-ttu-id="6b118-187">Eine öffentliche Standardeigenschaft oder -methode darf den gleichen Namen wie eine vorhandene Eigenschaft oder Methode aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b118-187">It is possible for a standard public property or method to have the same name as an existing property or method.</span></span> <span data-ttu-id="6b118-188">In diesem Fall wird der Name der Eigenschaft oder Methode in der generierten Klasse geändert, um Namenskonflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6b118-188">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="6b118-189">Der Name einer Eigenschaft oder Methode in einer generierten Klasse darf ein Schlüsselwort der Zielprogrammiersprache sein.</span><span class="sxs-lookup"><span data-stu-id="6b118-189">It is possible for the name of a property or method in a generated class to be a keyword in the target programming language.</span></span> <span data-ttu-id="6b118-190">In diesem Fall wird der Name der Eigenschaft oder Methode in der generierten Klasse geändert, um Namenskonflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6b118-190">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="6b118-191">Qualifizierer in WMI sind Modifizierer, die Informationen zum Beschreiben einer Klasse, Instanz, Eigenschaft oder Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="6b118-191">In WMI, qualifiers are modifiers that contain information to describe a class, instance, property, or method.</span></span> <span data-ttu-id="6b118-192">In WMI werden Eigenschaften in einer generierten Klasse mithilfe von Standardqualifizierern wie **Read,** **Write** und **Key** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b118-192">WMI uses standard qualifiers such as **Read**, **Write**, and **Key** to describe a property in a generated class.</span></span> <span data-ttu-id="6b118-193">Beispiel: Eine Eigenschaft, die mit einem **Read**-Qualifizierer modifiziert wird, wird in der generierten Klasse nur mit einer **Get**-Eigenschaftenzugriffsmethode definiert.</span><span class="sxs-lookup"><span data-stu-id="6b118-193">For example, a property that is modified with a **Read** qualifier is defined only with a property **get** accessor in the generated class.</span></span> <span data-ttu-id="6b118-194">Da eine mit dem **Read**-Qualifizierer markierte Eigenschaft schreibgeschützt sein soll, ist keine **Set**-Zugriffsmethode definiert.</span><span class="sxs-lookup"><span data-stu-id="6b118-194">Because a property marked with the **Read** qualifier is intended to be read-only, a **set** accessor is not defined.</span></span>  
  
- <span data-ttu-id="6b118-195">Eine numerische Eigenschaft kann durch den **Values**-Qualifizierer und den **ValueMaps**-Qualifizierer modifiziert werden, um anzugeben, dass sie nur auf bestimmte zulässige Werte festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b118-195">A numeric property can be modified by the **Values** and **ValueMaps** qualifiers to indicate that the property can be set only to specified permissible values.</span></span> <span data-ttu-id="6b118-196">Mit diesen **Values** und **ValueMaps** wird eine Enumeration erstellt, und die Eigenschaft wird der Enumeration zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6b118-196">An enumeration is generated with these **Values** and **ValueMaps** and the property is mapped to the enumeration.</span></span>  
  
- <span data-ttu-id="6b118-197">Eine Klasse, die nur eine Instanz aufweisen darf, wird in WMI mit dem Begriff "Singleton" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6b118-197">The WMI uses the term singleton to describe a class that can have only one instance.</span></span> <span data-ttu-id="6b118-198">Der parameterlose Konstruktor für eine Singleton-Klasse initialisiert die Klasse daher zur einzigen Instanz dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="6b118-198">Therefore, the parameterless constructor for a singleton class will initialize the class to the only instance of the class.</span></span>  
  
- <span data-ttu-id="6b118-199">Eine WMI-Klasse kann über Eigenschaften verfügen, bei denen es sich um Objekte handelt.</span><span class="sxs-lookup"><span data-stu-id="6b118-199">A WMI class can have properties that are objects.</span></span> <span data-ttu-id="6b118-200">Wenn Sie für eine solche WMI-Klasse eine stark typisierte Klasse generieren, empfiehlt es sich, für die Typen der eingebetteten Objekteigenschaften stark typisierte Klassen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6b118-200">When you generate a strongly typed class for this type of WMI class, you should consider generating strongly typed classes for the types of the embedded object properties.</span></span> <span data-ttu-id="6b118-201">Dies ermöglicht Ihnen den stark typisierten Zugriff auf die eingebetteten Objekte.</span><span class="sxs-lookup"><span data-stu-id="6b118-201">This will allow you to access the embedded objects in a strongly typed manner.</span></span> <span data-ttu-id="6b118-202">Beachten Sie, dass der generierte Code den Typ des eingebetteten Objekts möglicherweise nicht erkennen kann.</span><span class="sxs-lookup"><span data-stu-id="6b118-202">Note that the generated code might not be able to detect the type of the embedded object.</span></span> <span data-ttu-id="6b118-203">In einem solchen Fall wird im generierten Code ein Kommentar erstellt, in dem Sie auf das Problem hingewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6b118-203">In this case, a comment will be created in the generated code to notify you of this issue.</span></span> <span data-ttu-id="6b118-204">Sie können den generierten Code dann ändern, um den Typ der Eigenschaft an den der anderen generierten Klasse anzugleichen.</span><span class="sxs-lookup"><span data-stu-id="6b118-204">You can then modify the generated code to type the property to the other generated class.</span></span>  
  
- <span data-ttu-id="6b118-205">Der Datenwert des CIM_DATETIME-Datentyps kann in WMI entweder einen bestimmten Zeitpunkt (Datum und Uhrzeit) oder ein Zeitintervall darstellen.</span><span class="sxs-lookup"><span data-stu-id="6b118-205">In WMI, the data value of the CIM_DATETIME data type can represent either a specific date and time or a time interval.</span></span> <span data-ttu-id="6b118-206">Wenn der Datenwert einen Zeitpunkt (Datum und Uhrzeit) darstellt, ist der Datentyp in der generierten Klasse **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="6b118-206">If the data value represents a date and time, the data type in the generated class is **DateTime**.</span></span> <span data-ttu-id="6b118-207">Wenn der Datenwert ein Zeitintervall darstellt, ist der Datentyp in der generierten Klasse **TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="6b118-207">If the data value represents a time interval, the data type in the generated class is **TimeSpan**.</span></span>  
  
 <span data-ttu-id="6b118-208">Es besteht auch die Möglichkeit, mithilfe der Verwaltungserweiterung für Server-Explorer in Visual Studio .NET eine stark typisierte Klasse zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6b118-208">You can alternately generate a strongly typed class using the Server Explorer Management Extension in Visual Studio .NET.</span></span>  
  
 <span data-ttu-id="6b118-209">Weitere Informationen zu WMI finden Sie im Thema **Windows-Verwaltungsinstrumentation** in der Platform SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b118-209">For more information about WMI, see the **Windows Management Instrumentation** topic in the Platform SDK documentation.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6b118-210">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6b118-210">Examples</span></span>  
 <span data-ttu-id="6b118-211">Der folgende Befehl generiert eine verwaltete Klasse in C#-Code für die **Win32_LogicalDisk**-WMI-Klasse im **Root\cimv2**-Namespace.</span><span class="sxs-lookup"><span data-stu-id="6b118-211">The following command generates a managed class in C# code for the **Win32_LogicalDisk** WMI class in the **Root\cimv2** namespace.</span></span> <span data-ttu-id="6b118-212">Das Tool schreibt die verwaltete Klasse in die Quelldatei, die sich unter „c:\disk.cs“ im **ROOT.CIMV2.Win32**-Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="6b118-212">The tool writes the managed class to the source file at c:\disk.cs in the **ROOT.CIMV2.Win32** namespace.</span></span>  
  
```console  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 <span data-ttu-id="6b118-213">Im folgenden Codebeispiel wird die programmgesteuerte Verwendung einer generierten Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6b118-213">The following code example shows how to use a generated class programmatically.</span></span> <span data-ttu-id="6b118-214">Zunächst wird eine Instanz der Klasse aufgelistet und der Pfad ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b118-214">First, an instance of the class is enumerated and the path is printed.</span></span> <span data-ttu-id="6b118-215">Anschließend wird eine Instanz der zu initialisierenden generierten Klasse mit einer Instanz von WMI erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b118-215">Next, an instance of the generated class to be initialized is created with an instance of WMI.</span></span> <span data-ttu-id="6b118-216">`Process` ist die für **Win32_Process** generierte Klasse, und `LogicalDisk` ist die für **Win32_LogicalDisk** im **Root\cimv2**-Namespace generierte Klasse.</span><span class="sxs-lookup"><span data-stu-id="6b118-216">`Process` is the class generated for **Win32_Process** and `LogicalDisk` is the class generated for **Win32_LogicalDisk** in the **Root\cimv2** namespace.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports ROOT.CIMV2.Win32  
  
Public Class App
   Public Shared Sub Main()
      ' Enumerate instances of the Win32_process.  
      ' Print the Name property of the instance.  
      Dim ps As Process
      For Each ps In  Process.GetInstances()  
         Console.WriteLine(ps.Name)  
      Next ps  
  
      ' Initialize the instance of LogicalDisk with  
      ' the WMI instance pointing to logical drive d:.  
      Dim dskD As New LogicalDisk(New _  
         ManagementPath("win32_LogicalDisk.DeviceId=""d:"""))  
      Console.WriteLine(dskD.Caption)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Management;  
using ROOT.CIMV2.Win32;  
  
public class App  
{  
   public static void Main()  
   {  
      // Enumerate instances of the Win32_process.  
      // Print the Name property of the instance.  
      foreach(Process ps in Process.GetInstances())  
      {  
         Console.WriteLine(ps.Name);  
      }  
  
      // Initialize the instance of LogicalDisk with  
      // the WMI instance pointing to logical drive d:.  
      LogicalDisk dskD = new LogicalDisk(new ManagementPath(  
        "win32_LogicalDisk.DeviceId=\"d:\""));  
      Console.WriteLine(dskD.Caption);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b118-217">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b118-217">See also</span></span>

- <xref:System.Management>
- <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>
- <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>
- [<span data-ttu-id="6b118-218">Extras</span><span class="sxs-lookup"><span data-stu-id="6b118-218">Tools</span></span>](index.md)
- [<span data-ttu-id="6b118-219">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="6b118-219">Command Prompts</span></span>](developer-command-prompt-for-vs.md)

---
title: Mgmtclassgen.exe (Management Strongly Typed Class Generator)
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
ms.openlocfilehash: 5e39670fbb40acb999a243ac86683219f3c89e4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180377"
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a><span data-ttu-id="14791-102">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span><span class="sxs-lookup"><span data-stu-id="14791-102">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>
<span data-ttu-id="14791-103">Mit dem Management Strongly Typed Class Generator-Tool können Sie schnell eine früh gebundene Klasse für eine angegebene WMI (Windows Management Instrumentation)-Klasse generieren.</span><span class="sxs-lookup"><span data-stu-id="14791-103">The Management Strongly Typed Class Generator tool enables you to quickly generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span> <span data-ttu-id="14791-104">Die generierte Klasse vereinfacht den Code, den Sie für den Zugriff auf eine Instanz der WMI-Klasse schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="14791-104">The generated class simplifies the code you must write to access an instance of the WMI class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14791-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="14791-105">Syntax</span></span>  
  
```console  
mgmtclassgen
WMIClass [options]
```  
  
|<span data-ttu-id="14791-106">Argument</span><span class="sxs-lookup"><span data-stu-id="14791-106">Argument</span></span>|<span data-ttu-id="14791-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14791-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="14791-108">*WMIClass*</span><span class="sxs-lookup"><span data-stu-id="14791-108">*WMIClass*</span></span>|<span data-ttu-id="14791-109">Die WMI (Windows Management Instrumentation)-Klasse, für die eine früh gebundene verwaltete Klasse generiert wird.</span><span class="sxs-lookup"><span data-stu-id="14791-109">The Windows Management Instrumentation class for which to generate an early-bound managed class.</span></span>|  
  
|<span data-ttu-id="14791-110">Option</span><span class="sxs-lookup"><span data-stu-id="14791-110">Option</span></span>|<span data-ttu-id="14791-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14791-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="14791-112">**/l**  *language*</span><span class="sxs-lookup"><span data-stu-id="14791-112">**/l**  *language*</span></span>|<span data-ttu-id="14791-113">Gibt die Programmiersprache an, in der die früh gebundene verwaltete Klasse generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="14791-113">Specifies the language in which to generate the early-bound managed class.</span></span> <span data-ttu-id="14791-114">Als Sprachargument können Sie **CS** (C#, Standard), **VB** (Visual Basic), **MC** (C++) oder **JS** (JScript) festlegen.</span><span class="sxs-lookup"><span data-stu-id="14791-114">You can specify **CS** (C#; default), **VB** (Visual Basic),  **MC** (C++), or **JS** (JScript) as the language argument.</span></span>|  
|<span data-ttu-id="14791-115">**/m**  *machine*</span><span class="sxs-lookup"><span data-stu-id="14791-115">**/m**  *machine*</span></span>|<span data-ttu-id="14791-116">Gibt den Computer an, auf dem sich die WMI-Klasse befindet und mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="14791-116">Specifies the computer to connect to, where the WMI class resides.</span></span> <span data-ttu-id="14791-117">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="14791-117">The default is the local computer.</span></span>|  
|<span data-ttu-id="14791-118">**/n**  *path*</span><span class="sxs-lookup"><span data-stu-id="14791-118">**/n**  *path*</span></span>|<span data-ttu-id="14791-119">Gibt den Pfad zum WMI-Namespace an, der die WMI-Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="14791-119">Specifies the path to the WMI namespace that contains the WMI class.</span></span> <span data-ttu-id="14791-120">Wenn Sie keinen Pfad angeben, generiert das Tool den Code für *WMIClass* im Namespace **Root\cimv2-Standard**.</span><span class="sxs-lookup"><span data-stu-id="14791-120">If you do not specify this option, the tool generates code for *WMIClass* in the default **Root\cimv2** namespace.</span></span>|  
|<span data-ttu-id="14791-121">**/o**  *classnamespace*</span><span class="sxs-lookup"><span data-stu-id="14791-121">**/o**  *classnamespace*</span></span>|<span data-ttu-id="14791-122">Gibt den .NET-Namespace an, in dem die verwaltete Codeklasse generiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="14791-122">Specifies the .NET namespace in which to generate the managed code class.</span></span> <span data-ttu-id="14791-123">Wenn Sie keinen Klassennamespace angeben, generiert das Tool den Namespace aus dem WMI-Namespace und dem Schemapräfix.</span><span class="sxs-lookup"><span data-stu-id="14791-123">If you do not specify this option, the tool generates the namespace using the WMI namespace and the schema prefix.</span></span> <span data-ttu-id="14791-124">Das Schemapräfix ist der Bestandteil des Klassennamens, der dem Unterstrich vorangeht.</span><span class="sxs-lookup"><span data-stu-id="14791-124">The schema prefix is the part of the class name preceding the underscore character.</span></span> <span data-ttu-id="14791-125">Für die **Win32_OperatingSystem**-Klasse im **Root\cimv2**-Namespace würde die Klasse beispielsweise in **ROOT.CIMV2.Win32** generiert werden.</span><span class="sxs-lookup"><span data-stu-id="14791-125">For example, for the **Win32_OperatingSystem** class in the **Root\cimv2** namespace, the tool would generate the class in **ROOT.CIMV2.Win32**.</span></span>|  
|<span data-ttu-id="14791-126">**/p**  *filepath*</span><span class="sxs-lookup"><span data-stu-id="14791-126">**/p**  *filepath*</span></span>|<span data-ttu-id="14791-127">Gibt den Pfad zur Datei an, in der der generierte Code gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="14791-127">Specifies the path to the file in which to save the generated code.</span></span> <span data-ttu-id="14791-128">Wenn Sie keinen Dateipfad angeben, erstellt das Tool die Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="14791-128">If you do not specify this option, the tool creates the file in the current directory.</span></span> <span data-ttu-id="14791-129">Es benennt die Klasse und die Datei, in der diese erstellt wird, anhand des *WMIClass*-Arguments.</span><span class="sxs-lookup"><span data-stu-id="14791-129">It names the class and file in which it generates the class using the *WMIClass* argument.</span></span> <span data-ttu-id="14791-130">Die Namen der Klasse und der Datei stimmen mit dem Namen der *WMIClass* überein.</span><span class="sxs-lookup"><span data-stu-id="14791-130">The name of the class and the file are the same as the name of the *WMIClass.*</span></span> <span data-ttu-id="14791-131">Wenn *WMIClass* einen Unterstrich enthält, wird der Teil des Namens nach dem Unterstrich verwendet.</span><span class="sxs-lookup"><span data-stu-id="14791-131">If *WMIClass* contains an underscore character, the tool uses the part of the class name following the underscore character.</span></span> <span data-ttu-id="14791-132">Wenn etwa der *WMIClass*-Name das Format **Win32_LogicalDisk** aufweist, werden die generierte Klasse und Datei mit „logicaldisk“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="14791-132">For example, if the *WMIClass* name is in the format **Win32_LogicalDisk**, the generated class and file is named "logicaldisk".</span></span> <span data-ttu-id="14791-133">Wenn bereits eine gleichnamige Datei vorhanden ist, wird diese überschrieben.</span><span class="sxs-lookup"><span data-stu-id="14791-133">If a file already exists, the tool overwrites the existing file.</span></span>|  
|<span data-ttu-id="14791-134">**/pw**  *password*</span><span class="sxs-lookup"><span data-stu-id="14791-134">**/pw**  *password*</span></span>|<span data-ttu-id="14791-135">Gibt das Kennwort für die Anmeldung an einem Computer an, der durch die **/m**-Option angegeben ist</span><span class="sxs-lookup"><span data-stu-id="14791-135">Specifies the password to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="14791-136">**/u**  *user name*</span><span class="sxs-lookup"><span data-stu-id="14791-136">**/u**  *user name*</span></span>|<span data-ttu-id="14791-137">Gibt den Benutzernamen für die Anmeldung an einem Computer an, der durch die **/m**-Option angegeben ist</span><span class="sxs-lookup"><span data-stu-id="14791-137">Specifies the user name to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="14791-138">**/?**</span><span class="sxs-lookup"><span data-stu-id="14791-138">**/?**</span></span>|<span data-ttu-id="14791-139">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="14791-139">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14791-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14791-140">Remarks</span></span>  
 <span data-ttu-id="14791-141">"Mgmtclassgen.exe" verwendet die <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="14791-141">Mgmtclassgen.exe uses the <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="14791-142">Sie können daher mit einem beliebigen benutzerdefinierten Codeanbieter Code in anderen verwalteten Sprachen als C#, Visual Basic und JScript generieren.</span><span class="sxs-lookup"><span data-stu-id="14791-142">Therefore, you can use any custom code provider to generate code in managed languages other than C#, Visual Basic, and JScript.</span></span>  
  
 <span data-ttu-id="14791-143">Beachten Sie, dass die generierten Klassen an das Schema gebunden sind, für das sie generiert werden.</span><span class="sxs-lookup"><span data-stu-id="14791-143">Note that generated classes are bound to the schema for which they are generated.</span></span> <span data-ttu-id="14791-144">Änderungen am zugrunde liegenden Schema wirken sich auf die Klasse erst nach einer Neugenerierung aus.</span><span class="sxs-lookup"><span data-stu-id="14791-144">If the underlying schema changes, you must regenerate the class if you want it to reflect changes to the schema.</span></span>  
  
 <span data-ttu-id="14791-145">In der folgenden Tabelle wird die Zuordnung von WMI Common Information Model (CIM)-Typen zu Datentypen in einer generierten Klasse dargestellt:</span><span class="sxs-lookup"><span data-stu-id="14791-145">The following table shows how WMI Common Information Model (CIM) types map to data types in a generated class:</span></span>  
  
|<span data-ttu-id="14791-146">CIM-Typ</span><span class="sxs-lookup"><span data-stu-id="14791-146">CIM type</span></span>|<span data-ttu-id="14791-147">Datentyp in der generierten Klasse</span><span class="sxs-lookup"><span data-stu-id="14791-147">Data type in the generated class</span></span>|  
|--------------|--------------------------------------|  
|<span data-ttu-id="14791-148">CIM_SINT8</span><span class="sxs-lookup"><span data-stu-id="14791-148">CIM_SINT8</span></span>|<span data-ttu-id="14791-149">**SByte**</span><span class="sxs-lookup"><span data-stu-id="14791-149">**SByte**</span></span>|  
|<span data-ttu-id="14791-150">CIM_UINT8</span><span class="sxs-lookup"><span data-stu-id="14791-150">CIM_UINT8</span></span>|<span data-ttu-id="14791-151">**Byte**</span><span class="sxs-lookup"><span data-stu-id="14791-151">**Byte**</span></span>|  
|<span data-ttu-id="14791-152">CIM_SINT16</span><span class="sxs-lookup"><span data-stu-id="14791-152">CIM_SINT16</span></span>|<span data-ttu-id="14791-153">**Int16**</span><span class="sxs-lookup"><span data-stu-id="14791-153">**Int16**</span></span>|  
|<span data-ttu-id="14791-154">CIM_UINT16</span><span class="sxs-lookup"><span data-stu-id="14791-154">CIM_UINT16</span></span>|<span data-ttu-id="14791-155">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="14791-155">**UInt16**</span></span>|  
|<span data-ttu-id="14791-156">CIM_SINT32</span><span class="sxs-lookup"><span data-stu-id="14791-156">CIM_SINT32</span></span>|<span data-ttu-id="14791-157">**Int32**</span><span class="sxs-lookup"><span data-stu-id="14791-157">**Int32**</span></span>|  
|<span data-ttu-id="14791-158">SIM_UINT32</span><span class="sxs-lookup"><span data-stu-id="14791-158">SIM_UINT32</span></span>|<span data-ttu-id="14791-159">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="14791-159">**UInt32**</span></span>|  
|<span data-ttu-id="14791-160">CIM_SINT64</span><span class="sxs-lookup"><span data-stu-id="14791-160">CIM_SINT64</span></span>|<span data-ttu-id="14791-161">**Int64**</span><span class="sxs-lookup"><span data-stu-id="14791-161">**Int64**</span></span>|  
|<span data-ttu-id="14791-162">CIM_UINT64</span><span class="sxs-lookup"><span data-stu-id="14791-162">CIM_UINT64</span></span>|<span data-ttu-id="14791-163">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="14791-163">**UInt64**</span></span>|  
|<span data-ttu-id="14791-164">CIM_REAL32</span><span class="sxs-lookup"><span data-stu-id="14791-164">CIM_REAL32</span></span>|<span data-ttu-id="14791-165">**Single**</span><span class="sxs-lookup"><span data-stu-id="14791-165">**Single**</span></span>|  
|<span data-ttu-id="14791-166">CIM_REAL64</span><span class="sxs-lookup"><span data-stu-id="14791-166">CIM_REAL64</span></span>|<span data-ttu-id="14791-167">**Double**</span><span class="sxs-lookup"><span data-stu-id="14791-167">**Double**</span></span>|  
|<span data-ttu-id="14791-168">CIM_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="14791-168">CIM_BOOLEAN</span></span>|<span data-ttu-id="14791-169">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="14791-169">**Boolean**</span></span>|  
|<span data-ttu-id="14791-170">CIM_String</span><span class="sxs-lookup"><span data-stu-id="14791-170">CIM_String</span></span>|<span data-ttu-id="14791-171">**String**</span><span class="sxs-lookup"><span data-stu-id="14791-171">**String**</span></span>|  
|<span data-ttu-id="14791-172">CIM_DATETIME</span><span class="sxs-lookup"><span data-stu-id="14791-172">CIM_DATETIME</span></span>|<span data-ttu-id="14791-173">**DateTime** oder **TimeSpan**</span><span class="sxs-lookup"><span data-stu-id="14791-173">**DateTime** or **TimeSpan**</span></span>|  
|<span data-ttu-id="14791-174">CIM_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="14791-174">CIM_REFERENCE</span></span>|<span data-ttu-id="14791-175">**ManagementPath**</span><span class="sxs-lookup"><span data-stu-id="14791-175">**ManagementPath**</span></span>|  
|<span data-ttu-id="14791-176">CIM_CHAR16</span><span class="sxs-lookup"><span data-stu-id="14791-176">CIM_CHAR16</span></span>|<span data-ttu-id="14791-177">**Char**</span><span class="sxs-lookup"><span data-stu-id="14791-177">**Char**</span></span>|  
|<span data-ttu-id="14791-178">CIM_OBJECT</span><span class="sxs-lookup"><span data-stu-id="14791-178">CIM_OBJECT</span></span>|<span data-ttu-id="14791-179">**ManagementBaseObject**</span><span class="sxs-lookup"><span data-stu-id="14791-179">**ManagementBaseObject**</span></span>|  
|<span data-ttu-id="14791-180">CIM_IUNKNOWN</span><span class="sxs-lookup"><span data-stu-id="14791-180">CIM_IUNKNOWN</span></span>|<span data-ttu-id="14791-181">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="14791-181">**Object**</span></span>|  
|<span data-ttu-id="14791-182">CIM_ARRAY</span><span class="sxs-lookup"><span data-stu-id="14791-182">CIM_ARRAY</span></span>|<span data-ttu-id="14791-183">Array der zuvor aufgeführten Objekte</span><span class="sxs-lookup"><span data-stu-id="14791-183">Array of the above mentioned objects</span></span>|  
  
 <span data-ttu-id="14791-184">Beim Generieren einer WMI-Klasse werden Sie folgende Verhaltensweisen feststellen:</span><span class="sxs-lookup"><span data-stu-id="14791-184">Note the following behaviors when you generate a WMI class:</span></span>  
  
- <span data-ttu-id="14791-185">Eine öffentliche Standardeigenschaft oder -methode darf den gleichen Namen wie eine vorhandene Eigenschaft oder Methode aufweisen.</span><span class="sxs-lookup"><span data-stu-id="14791-185">It is possible for a standard public property or method to have the same name as an existing property or method.</span></span> <span data-ttu-id="14791-186">In diesem Fall wird der Name der Eigenschaft oder Methode in der generierten Klasse geändert, um Namenskonflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="14791-186">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="14791-187">Der Name einer Eigenschaft oder Methode in einer generierten Klasse darf ein Schlüsselwort der Zielprogrammiersprache sein.</span><span class="sxs-lookup"><span data-stu-id="14791-187">It is possible for the name of a property or method in a generated class to be a keyword in the target programming language.</span></span> <span data-ttu-id="14791-188">In diesem Fall wird der Name der Eigenschaft oder Methode in der generierten Klasse geändert, um Namenskonflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="14791-188">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="14791-189">Qualifizierer in WMI sind Modifizierer, die Informationen zum Beschreiben einer Klasse, Instanz, Eigenschaft oder Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="14791-189">In WMI, qualifiers are modifiers that contain information to describe a class, instance, property, or method.</span></span> <span data-ttu-id="14791-190">In WMI werden Eigenschaften in einer generierten Klasse mithilfe von Standardqualifizierern wie **Read,** **Write** und **Key** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14791-190">WMI uses standard qualifiers such as **Read**, **Write**, and **Key** to describe a property in a generated class.</span></span> <span data-ttu-id="14791-191">Beispiel: Eine Eigenschaft, die mit einem **Read**-Qualifizierer modifiziert wird, wird in der generierten Klasse nur mit einer **Get**-Eigenschaftenzugriffsmethode definiert.</span><span class="sxs-lookup"><span data-stu-id="14791-191">For example, a property that is modified with a **Read** qualifier is defined only with a property **get** accessor in the generated class.</span></span> <span data-ttu-id="14791-192">Da eine mit dem **Read**-Qualifizierer markierte Eigenschaft schreibgeschützt sein soll, ist keine **Set**-Zugriffsmethode definiert.</span><span class="sxs-lookup"><span data-stu-id="14791-192">Because a property marked with the **Read** qualifier is intended to be read-only, a **set** accessor is not defined.</span></span>  
  
- <span data-ttu-id="14791-193">Eine numerische Eigenschaft kann durch den **Values**-Qualifizierer und den **ValueMaps**-Qualifizierer modifiziert werden, um anzugeben, dass sie nur auf bestimmte zulässige Werte festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="14791-193">A numeric property can be modified by the **Values** and **ValueMaps** qualifiers to indicate that the property can be set only to specified permissible values.</span></span> <span data-ttu-id="14791-194">Mit diesen **Values** und **ValueMaps** wird eine Enumeration erstellt, und die Eigenschaft wird der Enumeration zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="14791-194">An enumeration is generated with these **Values** and **ValueMaps** and the property is mapped to the enumeration.</span></span>  
  
- <span data-ttu-id="14791-195">Eine Klasse, die nur eine Instanz aufweisen darf, wird in WMI mit dem Begriff "Singleton" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="14791-195">The WMI uses the term singleton to describe a class that can have only one instance.</span></span> <span data-ttu-id="14791-196">Der parameterlose Konstruktor für eine Singleton-Klasse initialisiert die Klasse daher zur einzigen Instanz dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="14791-196">Therefore, the parameterless constructor for a singleton class will initialize the class to the only instance of the class.</span></span>  
  
- <span data-ttu-id="14791-197">Eine WMI-Klasse kann über Eigenschaften verfügen, bei denen es sich um Objekte handelt.</span><span class="sxs-lookup"><span data-stu-id="14791-197">A WMI class can have properties that are objects.</span></span> <span data-ttu-id="14791-198">Wenn Sie für eine solche WMI-Klasse eine stark typisierte Klasse generieren, empfiehlt es sich, für die Typen der eingebetteten Objekteigenschaften stark typisierte Klassen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="14791-198">When you generate a strongly-typed class for this type of WMI class, you should consider generating strongly-typed classes for the types of the embedded object properties.</span></span> <span data-ttu-id="14791-199">Dies ermöglicht Ihnen den stark typisierten Zugriff auf die eingebetteten Objekte.</span><span class="sxs-lookup"><span data-stu-id="14791-199">This will allow you to access the embedded objects in a strongly-typed manner.</span></span> <span data-ttu-id="14791-200">Beachten Sie, dass der generierte Code den Typ des eingebetteten Objekts möglicherweise nicht erkennen kann.</span><span class="sxs-lookup"><span data-stu-id="14791-200">Note that the generated code might not be able to detect the type of the embedded object.</span></span> <span data-ttu-id="14791-201">In einem solchen Fall wird im generierten Code ein Kommentar erstellt, in dem Sie auf das Problem hingewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="14791-201">In this case, a comment will be created in the generated code to notify you of this issue.</span></span> <span data-ttu-id="14791-202">Sie können den generierten Code dann ändern, um den Typ der Eigenschaft an den der anderen generierten Klasse anzugleichen.</span><span class="sxs-lookup"><span data-stu-id="14791-202">You can then modify the generated code to type the property to the other generated class.</span></span>  
  
- <span data-ttu-id="14791-203">Der Datenwert des CIM_DATETIME-Datentyps kann in WMI entweder einen bestimmten Zeitpunkt (Datum und Uhrzeit) oder ein Zeitintervall darstellen.</span><span class="sxs-lookup"><span data-stu-id="14791-203">In WMI, the data value of the CIM_DATETIME data type can represent either a specific date and time or a time interval.</span></span> <span data-ttu-id="14791-204">Wenn der Datenwert einen Zeitpunkt (Datum und Uhrzeit) darstellt, ist der Datentyp in der generierten Klasse **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="14791-204">If the data value represents a date and time, the data type in the generated class is **DateTime**.</span></span> <span data-ttu-id="14791-205">Wenn der Datenwert ein Zeitintervall darstellt, ist der Datentyp in der generierten Klasse **TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="14791-205">If the data value represents a time interval, the data type in the generated class is **TimeSpan**.</span></span>  
  
 <span data-ttu-id="14791-206">Es besteht auch die Möglichkeit, mithilfe der Verwaltungserweiterung für Server-Explorer in Visual Studio .NET eine stark typisierte Klasse zu generieren.</span><span class="sxs-lookup"><span data-stu-id="14791-206">You can alternately generate a strongly-typed class using the Server Explorer Management Extension in Visual Studio .NET.</span></span>  
  
 <span data-ttu-id="14791-207">Weitere Informationen zu WMI finden Sie im Thema **Windows-Verwaltungsinstrumentation** in der Platform SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="14791-207">For more information about WMI, see the **Windows Management Instrumentation** topic in the Platform SDK documentation.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="14791-208">Beispiele</span><span class="sxs-lookup"><span data-stu-id="14791-208">Examples</span></span>  
 <span data-ttu-id="14791-209">Der folgende Befehl generiert eine verwaltete Klasse in C#-Code für die **Win32_LogicalDisk**-WMI-Klasse im **Root\cimv2**-Namespace.</span><span class="sxs-lookup"><span data-stu-id="14791-209">The following command generates a managed class in C# code for the **Win32_LogicalDisk** WMI class in the **Root\cimv2** namespace.</span></span> <span data-ttu-id="14791-210">Das Tool schreibt die verwaltete Klasse in die Quelldatei, die sich unter „c:\disk.cs“ im **ROOT.CIMV2.Win32**-Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="14791-210">The tool writes the managed class to the source file at c:\disk.cs in the **ROOT.CIMV2.Win32** namespace.</span></span>  
  
```console  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 <span data-ttu-id="14791-211">Im folgenden Codebeispiel wird die programmgesteuerte Verwendung einer generierten Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="14791-211">The following code example shows how to use a generated class programmatically.</span></span> <span data-ttu-id="14791-212">Zunächst wird eine Instanz der Klasse aufgelistet und der Pfad ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="14791-212">First, an instance of the class is enumerated and the path is printed.</span></span> <span data-ttu-id="14791-213">Anschließend wird eine Instanz der zu initialisierenden generierten Klasse mit einer Instanz von WMI erstellt.</span><span class="sxs-lookup"><span data-stu-id="14791-213">Next, an instance of the generated class to be initialized is created with an instance of WMI.</span></span> <span data-ttu-id="14791-214">`Process` ist die für **Win32_Process** generierte Klasse, und `LogicalDisk` ist die für **Win32_LogicalDisk** im **Root\cimv2**-Namespace generierte Klasse.</span><span class="sxs-lookup"><span data-stu-id="14791-214">`Process` is the class generated for **Win32_Process** and `LogicalDisk` is the class generated for **Win32_LogicalDisk** in the **Root\cimv2** namespace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14791-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14791-215">See also</span></span>

- <xref:System.Management>
- <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>
- <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>
- [<span data-ttu-id="14791-216">Extras</span><span class="sxs-lookup"><span data-stu-id="14791-216">Tools</span></span>](index.md)
- [<span data-ttu-id="14791-217">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="14791-217">Command Prompts</span></span>](developer-command-prompt-for-vs.md)

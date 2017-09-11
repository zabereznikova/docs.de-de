---
title: 'Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="91626-102">Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="91626-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="91626-103">Das folgende Beispiel bietet eine grundlegende Übersicht über einen Typ, der dokumentierten wurde.</span><span class="sxs-lookup"><span data-stu-id="91626-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91626-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91626-104">Example</span></span>  
 <span data-ttu-id="91626-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="91626-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span></span>  
  
 <span data-ttu-id="91626-106">**// Diese XML-Datei wurde mit dem vorherigen Codebeispiel generiert.**</span><span class="sxs-lookup"><span data-stu-id="91626-106">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="91626-107">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="91626-107">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="91626-108">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="91626-108">**\<doc>**</span></span>  
 <span data-ttu-id="91626-109">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="91626-109">**\<assembly>**</span></span>  
 <span data-ttu-id="91626-110">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="91626-110">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="91626-111">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="91626-111">**\</assembly>**</span></span>  
 <span data-ttu-id="91626-112">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="91626-112">**\<members>**</span></span>  
 <span data-ttu-id="91626-113">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="91626-113">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="91626-114">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-114">**\<summary>**</span></span>  
 <span data-ttu-id="91626-115">**Hier eine Zusammenfassung der Klassenebene dokumentieren.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-115">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="91626-116">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="91626-116">**\<remarks>**</span></span>  
 <span data-ttu-id="91626-117">**Mit den remarks-Tags können einem Typ oder Member längere** </span><span class="sxs-lookup"><span data-stu-id="91626-117">**Longer comments can be associated with a type or member** </span></span>  
 <span data-ttu-id="91626-118">**Kommentare zugeordnet werden.\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="91626-118">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="91626-119">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91626-119">**\</member>**</span></span>  
 <span data-ttu-id="91626-120">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="91626-120">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="91626-121">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-121">**\<summary>**</span></span>  
 <span data-ttu-id="91626-122">**Speicher für die Name-Eigenschaft\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-122">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="91626-123">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91626-123">**\</member>**</span></span>  
 <span data-ttu-id="91626-124">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="91626-124">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="91626-125">**\<summary>Konstruktor der Klasse.\</summary>** </span><span class="sxs-lookup"><span data-stu-id="91626-125">**\<summary>The class constructor.\</summary>** </span></span>  
 <span data-ttu-id="91626-126">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91626-126">**\</member>**</span></span>  
 <span data-ttu-id="91626-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="91626-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="91626-128">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-128">**\<summary>**</span></span>  
 <span data-ttu-id="91626-129">**Beschreibung von SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-129">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="91626-130">**\<param name="s">Hier Beschreibung für den Parameter „s“ einfügen.\</param>**</span><span class="sxs-lookup"><span data-stu-id="91626-130">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="91626-131">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="91626-131">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="91626-132">**Sie können für alle Tags das cref-Attribut verwenden, um auf einen Typ oder Member** </span><span class="sxs-lookup"><span data-stu-id="91626-132">**You can use the cref attribute on any tag to reference a type or member** </span></span>  
 <span data-ttu-id="91626-133">**zu verweisen. Der Compiler prüft dann, ob der Verweis vorhanden ist. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="91626-133">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="91626-134">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91626-134">**\</member>**</span></span>  
 <span data-ttu-id="91626-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="91626-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="91626-136">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-136">**\<summary>**</span></span>  
 <span data-ttu-id="91626-137">**Eine andere Methode. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-137">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="91626-138">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="91626-138">**\<returns>**</span></span>  
 <span data-ttu-id="91626-139">**Rückgabeergebnisse werden mit returns-Tags beschrieben.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="91626-139">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="91626-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="91626-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="91626-141">**Beachten Sie die Verwendung des cref-Attributs, um auf eine bestimmte Methode zu verweisen.\</seealso>**</span><span class="sxs-lookup"><span data-stu-id="91626-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="91626-142">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91626-142">**\</member>**</span></span>  
 <span data-ttu-id="91626-143">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="91626-143">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="91626-144">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-144">**\<summary>**</span></span>  
 <span data-ttu-id="91626-145">**Der Einstiegspunkt der Anwendung.**</span><span class="sxs-lookup"><span data-stu-id="91626-145">**The entry point for the application.**</span></span>  
 <span data-ttu-id="91626-146">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-146">**\</summary>**</span></span>  
 <span data-ttu-id="91626-147">**\<param name="args"> Eine Liste der Befehlszeilenargumente.\</param>**</span><span class="sxs-lookup"><span data-stu-id="91626-147">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="91626-148">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91626-148">**\</member>**</span></span>  
 <span data-ttu-id="91626-149">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="91626-149">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="91626-150">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-150">**\<summary>**</span></span>  
 <span data-ttu-id="91626-151">**Name-Eigenschaft \</summary>**</span><span class="sxs-lookup"><span data-stu-id="91626-151">**Name property \</summary>**</span></span>  
 <span data-ttu-id="91626-152">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="91626-152">**\<value>**</span></span>  
 <span data-ttu-id="91626-153">**Der Eigenschaftswert wird mit value-Tags beschrieben.\</value>**</span><span class="sxs-lookup"><span data-stu-id="91626-153">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="91626-154">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="91626-154">**\</member>**</span></span>  
 <span data-ttu-id="91626-155">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="91626-155">**\</members>**</span></span>  
<span data-ttu-id="91626-156">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="91626-156">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="91626-157">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="91626-157">Compiling the Code</span></span>  
 <span data-ttu-id="91626-158">Geben Sie die folgende Befehlszeile ein, um das Beispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="91626-158">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="91626-159">Dadurch wird die XML-Datei „XMLsample.xml“ erstellt, die Sie in Ihrem Browser oder mithilfe des TYPE-Befehls anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="91626-159">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="91626-160">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="91626-160">Robust Programming</span></span>  
 <span data-ttu-id="91626-161">XML-Dokumentation beginnt mit ///.</span><span class="sxs-lookup"><span data-stu-id="91626-161">XML documentation starts with ///.</span></span> <span data-ttu-id="91626-162">Wenn Sie ein neues Projekt erstellen, fügt der Assistent einige ///-Startzeilen für Sie ein.</span><span class="sxs-lookup"><span data-stu-id="91626-162">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="91626-163">Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="91626-163">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="91626-164">Die Dokumentation muss wohlgeformtes XML sein.</span><span class="sxs-lookup"><span data-stu-id="91626-164">The documentation must be well-formed XML.</span></span> <span data-ttu-id="91626-165">Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="91626-165">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="91626-166">Entwickler können ihren eigenen Satz von Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="91626-166">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="91626-167">Es gibt ein Reihe empfohlener Tags (siehe Abschnitt „Weiterführende Themen“).</span><span class="sxs-lookup"><span data-stu-id="91626-167">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="91626-168">Einige der empfohlenen Tags haben eine besondere Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="91626-168">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="91626-169">Das \<param>-Tag wird verwendet, um Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="91626-169">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="91626-170">Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="91626-170">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="91626-171">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="91626-171">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="91626-172">Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="91626-172">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="91626-173">Der Compiler überprüft, ob dieses Codeelement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="91626-173">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="91626-174">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="91626-174">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="91626-175">Der Compiler berücksichtigt alle `using`-Anweisungen, wenn er nach einem Typ sucht, der im `cref`-Attribut beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="91626-175">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="91626-176">Das \<summary>-Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen über einen Typ oder Member anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91626-176">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="91626-177">Die XML-Datei enthält keine vollständigen Informationen über den Typ und die Member (z. B. fehlen Typinformationen).</span><span class="sxs-lookup"><span data-stu-id="91626-177">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="91626-178">Um vollständige Informationen zu einem Typ oder Member zu erhalten, muss die Dokumentationsdatei zusammen mit Reflektion über den tatsächlichen Typ oder Member verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91626-178">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91626-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91626-179">See Also</span></span>  
 <span data-ttu-id="91626-180">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="91626-180">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="91626-181">[/doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="91626-181">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="91626-182">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="91626-182">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)


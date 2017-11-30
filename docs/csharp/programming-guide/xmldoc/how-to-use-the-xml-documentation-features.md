---
title: 'Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb647a275a5cd5fac2316706591440d9792861b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="40347-102">Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="40347-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="40347-103">Das folgende Beispiel bietet eine grundlegende Übersicht über einen Typ, der dokumentierten wurde.</span><span class="sxs-lookup"><span data-stu-id="40347-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40347-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40347-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 <span data-ttu-id="40347-105">**// Diese XML-Datei wurde mit dem vorherigen Codebeispiel generiert.**</span><span class="sxs-lookup"><span data-stu-id="40347-105">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="40347-106">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="40347-106">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="40347-107">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="40347-107">**\<doc>**</span></span>  
 <span data-ttu-id="40347-108">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="40347-108">**\<assembly>**</span></span>  
 <span data-ttu-id="40347-109">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="40347-109">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="40347-110">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="40347-110">**\</assembly>**</span></span>  
 <span data-ttu-id="40347-111">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="40347-111">**\<members>**</span></span>  
 <span data-ttu-id="40347-112">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="40347-112">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="40347-113">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-113">**\<summary>**</span></span>  
 <span data-ttu-id="40347-114">**Hier eine Zusammenfassung der Klassenebene dokumentieren.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-114">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="40347-115">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="40347-115">**\<remarks>**</span></span>  
 <span data-ttu-id="40347-116">**Längere Kommentare können einen Typ oder Member zugeordnet werden.**</span><span class="sxs-lookup"><span data-stu-id="40347-116">**Longer comments can be associated with a type or member**</span></span>  
 <span data-ttu-id="40347-117">**Kommentare zugeordnet werden.\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="40347-117">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="40347-118">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="40347-118">**\</member>**</span></span>  
 <span data-ttu-id="40347-119">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="40347-119">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="40347-120">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-120">**\<summary>**</span></span>  
 <span data-ttu-id="40347-121">**Speicher für die Name-Eigenschaft\</summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-121">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="40347-122">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="40347-122">**\</member>**</span></span>  
 <span data-ttu-id="40347-123">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="40347-123">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="40347-124">**\<Zusammenfassung > Klassenkonstruktor.  \< /summary >**</span><span class="sxs-lookup"><span data-stu-id="40347-124">**\<summary>The class constructor.\</summary>**</span></span>  
 <span data-ttu-id="40347-125">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="40347-125">**\</member>**</span></span>  
 <span data-ttu-id="40347-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="40347-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="40347-127">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-127">**\<summary>**</span></span>  
 <span data-ttu-id="40347-128">**Beschreibung von SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-128">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="40347-129">**\<param name="s">Hier Beschreibung für den Parameter „s“ einfügen.\</param>**</span><span class="sxs-lookup"><span data-stu-id="40347-129">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="40347-130">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="40347-130">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="40347-131">**Sie können auf einem beliebigen Tag Cref-Attribut verwenden, auf einen Typ oder Member verweisen**</span><span class="sxs-lookup"><span data-stu-id="40347-131">**You can use the cref attribute on any tag to reference a type or member**</span></span>  
 <span data-ttu-id="40347-132">**zu verweisen. Der Compiler prüft dann, ob der Verweis vorhanden ist. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="40347-132">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="40347-133">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="40347-133">**\</member>**</span></span>  
 <span data-ttu-id="40347-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="40347-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="40347-135">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-135">**\<summary>**</span></span>  
 <span data-ttu-id="40347-136">**Eine andere Methode. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-136">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="40347-137">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="40347-137">**\<returns>**</span></span>  
 <span data-ttu-id="40347-138">**Rückgabeergebnisse werden mit returns-Tags beschrieben.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="40347-138">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="40347-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="40347-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="40347-140">**Beachten Sie die Verwendung des cref-Attributs, um auf eine bestimmte Methode zu verweisen.\</seealso>**</span><span class="sxs-lookup"><span data-stu-id="40347-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="40347-141">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="40347-141">**\</member>**</span></span>  
 <span data-ttu-id="40347-142">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="40347-142">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="40347-143">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-143">**\<summary>**</span></span>  
 <span data-ttu-id="40347-144">**Der Einstiegspunkt der Anwendung.**</span><span class="sxs-lookup"><span data-stu-id="40347-144">**The entry point for the application.**</span></span>  
 <span data-ttu-id="40347-145">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-145">**\</summary>**</span></span>  
 <span data-ttu-id="40347-146">**\<param name="args"> Eine Liste der Befehlszeilenargumente.\</param>**</span><span class="sxs-lookup"><span data-stu-id="40347-146">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="40347-147">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="40347-147">**\</member>**</span></span>  
 <span data-ttu-id="40347-148">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="40347-148">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="40347-149">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-149">**\<summary>**</span></span>  
 <span data-ttu-id="40347-150">**Name-Eigenschaft \</summary>**</span><span class="sxs-lookup"><span data-stu-id="40347-150">**Name property \</summary>**</span></span>  
 <span data-ttu-id="40347-151">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="40347-151">**\<value>**</span></span>  
 <span data-ttu-id="40347-152">**Der Eigenschaftswert wird mit value-Tags beschrieben.\</value>**</span><span class="sxs-lookup"><span data-stu-id="40347-152">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="40347-153">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="40347-153">**\</member>**</span></span>  
 <span data-ttu-id="40347-154">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="40347-154">**\</members>**</span></span>  
<span data-ttu-id="40347-155">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="40347-155">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="40347-156">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="40347-156">Compiling the Code</span></span>  
 <span data-ttu-id="40347-157">Geben Sie die folgende Befehlszeile ein, um das Beispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="40347-157">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="40347-158">Dadurch wird die XML-Datei „XMLsample.xml“ erstellt, die Sie in Ihrem Browser oder mithilfe des TYPE-Befehls anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="40347-158">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="40347-159">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="40347-159">Robust Programming</span></span>  
 <span data-ttu-id="40347-160">XML-Dokumentation beginnt mit ///.</span><span class="sxs-lookup"><span data-stu-id="40347-160">XML documentation starts with ///.</span></span> <span data-ttu-id="40347-161">Wenn Sie ein neues Projekt erstellen, fügt der Assistent einige ///-Startzeilen für Sie ein.</span><span class="sxs-lookup"><span data-stu-id="40347-161">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="40347-162">Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="40347-162">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="40347-163">Die Dokumentation muss wohlgeformtes XML sein.</span><span class="sxs-lookup"><span data-stu-id="40347-163">The documentation must be well-formed XML.</span></span> <span data-ttu-id="40347-164">Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="40347-164">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="40347-165">Entwickler können ihren eigenen Satz von Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="40347-165">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="40347-166">Es gibt ein Reihe empfohlener Tags (siehe Abschnitt „Weiterführende Themen“).</span><span class="sxs-lookup"><span data-stu-id="40347-166">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="40347-167">Einige der empfohlenen Tags haben eine besondere Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="40347-167">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="40347-168">Das \<param>-Tag wird verwendet, um Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="40347-168">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="40347-169">Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="40347-169">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="40347-170">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="40347-170">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="40347-171">Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="40347-171">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="40347-172">Der Compiler überprüft, ob dieses Codeelement vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="40347-172">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="40347-173">Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="40347-173">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="40347-174">Der Compiler berücksichtigt alle `using`-Anweisungen, wenn er nach einem Typ sucht, der im `cref`-Attribut beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="40347-174">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="40347-175">Das \<summary>-Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen über einen Typ oder Member anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40347-175">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="40347-176">Die XML-Datei enthält keine vollständigen Informationen über den Typ und die Member (z. B. fehlen Typinformationen).</span><span class="sxs-lookup"><span data-stu-id="40347-176">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="40347-177">Um vollständige Informationen zu einem Typ oder Member zu erhalten, muss die Dokumentationsdatei zusammen mit Reflektion über den tatsächlichen Typ oder Member verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40347-177">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40347-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40347-178">See Also</span></span>  
 [<span data-ttu-id="40347-179">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="40347-179">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="40347-180">/ doc (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="40347-180">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="40347-181">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="40347-181">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

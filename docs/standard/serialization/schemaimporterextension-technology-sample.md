---
title: SchemaImporterExtension-Technologiebeispiel
ms.date: 03/30/2017
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
ms.openlocfilehash: d63461425fd0b3366d39892512577b0dd706de13
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490867"
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="39345-102">SchemaImporterExtension-Technologiebeispiel</span><span class="sxs-lookup"><span data-stu-id="39345-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="39345-103">Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="39345-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="39345-104">In diesem Beispiel wird ein benutzerdefiniertes <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>-Objekt dargestellt, das die Feinsteuerung für die Codegenerierung beim Importieren eines XML-Schemas zulässt.</span><span class="sxs-lookup"><span data-stu-id="39345-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="39345-105">In der Anwendung wird das Erstellen, Registrieren und Aufrufen dieser Erweiterung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39345-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="39345-106">So erstellen Sie das Beispiel mithilfe der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="39345-106">To build the sample using the command prompt</span></span>  
  
1. <span data-ttu-id="39345-107">Öffnen Sie ein Eingabeaufforderungsfenster, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="39345-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="39345-108">Geben Sie in der Befehlszeile **msbuild.exe OrderSchemaImporterExtension.sln** ein.</span><span class="sxs-lookup"><span data-stu-id="39345-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="39345-109">So erstellen Sie das Beispiel mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="39345-109">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="39345-110">Öffnen Sie den Datei-Explorer, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="39345-110">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="39345-111">Doppelklicken Sie auf das Symbol für OrderSchemaImporterExtension.sln, um die Datei in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="39345-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3. <span data-ttu-id="39345-112">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="39345-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="39345-113">Die Anwendung wird im Standardverzeichnis \bin oder \bin\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="39345-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="39345-114">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="39345-114">To run the sample</span></span>  
  
1. <span data-ttu-id="39345-115">Navigieren Sie mithilfe der Eingabeaufforderung zu dem Verzeichnis, das die neue ausführbare Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="39345-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2. <span data-ttu-id="39345-116">Geben Sie in der Befehlszeile **[Name der ausführbaren Datei]** ein.</span><span class="sxs-lookup"><span data-stu-id="39345-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39345-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39345-117">Remarks</span></span>  
 <span data-ttu-id="39345-118">Weitere Informationen zum Erstellen von binären Beispieldateien und zu Registrierungsschritten finden in den Kommentaren in den Quellcodedateien und in der Datei build.proj.</span><span class="sxs-lookup"><span data-stu-id="39345-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39345-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39345-119">See also</span></span>

- <xref:System.CodeDom.CodeCompileUnit>
- <xref:System.CodeDom.CodeNamespace>
- <xref:System.CodeDom.CodeNamespaceImport>
- <xref:Microsoft.CSharp.CSharpCodeProvider>
- <xref:System.Xml.Serialization.IXmlSerializable>
- <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>
- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- <xref:System.Web.Services.Description>
- <xref:System.Web.Services.Discovery>
- <xref:System.Xml.Serialization>
- <xref:System.Uri>
- <xref:Microsoft.VisualBasic.VBCodeProvider>
- <xref:System.Web.Services.Description.WebReference>
- <xref:System.Xml.Serialization.XmlSchemaImporter>

---
title: Benutzerdefinierte Serialisierungsreihenfolge mit "XmlSerializer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 16032a7df2df374d6201f8da18d563deceeeb5bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="12f14-102">Benutzerdefinierte Serialisierungsreihenfolge mit "XmlSerializer"</span><span class="sxs-lookup"><span data-stu-id="12f14-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="12f14-103">Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="12f14-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="12f14-104">Dieses Beispiel veranschaulicht die Steuerung der Reihenfolge serialisierter und deserialisierter Elemente für die XML-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="12f14-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="12f14-105">Weitere Informationen zur Serialisierung finden Sie in den Kommentaren der Quellcodedateien und der Datei "build.proj".</span><span class="sxs-lookup"><span data-stu-id="12f14-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="12f14-106">So erstellen Sie das Beispiel mithilfe der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="12f14-106">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="12f14-107">Öffnen Sie das Eingabeaufforderungsfenster, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="12f14-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="12f14-108">Geben Sie **msbuild CustomOrder.sln** in der Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="12f14-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="12f14-109">So erstellen Sie das Beispiel mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12f14-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="12f14-110">Öffnen Sie [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="12f14-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="12f14-111">Doppelklicken Sie auf das Symbol für CustomOrder.sln, um die Datei in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12f14-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="12f14-112">Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="12f14-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="12f14-113">Dieselbe Anwendung wird im Standardunterverzeichnis \bin oder \bin\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="12f14-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f14-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12f14-114">See Also</span></span>  
 [<span data-ttu-id="12f14-115">Einfache Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12f14-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="12f14-116">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12f14-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="12f14-117">Steuern der XML-Serialisierung mit Attributen</span><span class="sxs-lookup"><span data-stu-id="12f14-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="12f14-118">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12f14-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="12f14-119">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12f14-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="12f14-120">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12f14-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)

---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: d64be95f71f840e08ede63e1c1f14ee08e52ce97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592475"
---
# <a name="configurationcodegenerator"></a><span data-ttu-id="86e79-102">ConfigurationCodeGenerator</span><span class="sxs-lookup"><span data-stu-id="86e79-102">ConfigurationCodeGenerator</span></span>
<span data-ttu-id="86e79-103">Der ConfigurationCodeGenerator ist ein Tool, mit dem Sie Ihre Implementierungen von benutzerdefinierten Kanälen für das Konfigurationssystem verfügbar machen können.</span><span class="sxs-lookup"><span data-stu-id="86e79-103">The ConfigurationCodeGenerator is a tool that you can use to expose your custom channel implementations to the configuration system.</span></span> <span data-ttu-id="86e79-104">Auf diese Weise können Benutzer den benutzerdefinierten Kanal wie bei vom System bereitgestellten Bindungen (wie `NetTcpBinding`) oder benutzerdefinierten Bindungen mit dem `TcpTransportBindingElement` mithilfe einer .config-Datei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86e79-104">This allows users of your custom channel to configure your channel by using a .config file just as they would configure a system-provided binding such as `NetTcpBinding` or a custom binding using the `TcpTransportBindingElement`.</span></span>  
  
 <span data-ttu-id="86e79-105">Wenn Sie einen benutzerdefinierten Kanal schreiben und ihn mit einem neuen `BindingElement` oder einer neuen `Binding` für das Programmiermodell verfügbar machen, müssen Sie eine Reihe von Klassen erstellen, damit das `BindingElement` bzw. die `Binding` mit einer .config-Datei konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="86e79-105">When you write a custom channel and expose it to the programming model by using a new `BindingElement` or `Binding`, you must create a set of classes to make the `BindingElement` or `Binding` configurable using a .config file.</span></span> <span data-ttu-id="86e79-106">Mit dem Tool ConfigurationCodeGenerator können Sie diese Klassen generieren und Ihren Kunden die Arbeit erleichtern.</span><span class="sxs-lookup"><span data-stu-id="86e79-106">You can use the ConfigurationCodeGenerator tool to generate these classes and enhance your customer's experience.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="86e79-107">So erstellen Sie das Tool</span><span class="sxs-lookup"><span data-stu-id="86e79-107">To build the tool</span></span>  
  
1. <span data-ttu-id="86e79-108">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e79-108">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="86e79-109">Beim Erstellen der Projektmappe wird eine Datei generiert: ConfigurationCodeGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="86e79-109">Building the solution generates one file: ConfigurationCodeGenerator.exe.</span></span> <span data-ttu-id="86e79-110">Die Datei "SampleRun. cmd" verfügt über eine Beispiel Befehlszeile, die veranschaulicht, wie dieses Tool zum Generieren der Klassen für das " [Transport: UDP](transport-udp.md) "-Beispiel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86e79-110">The file SampleRun.cmd has a sample command line that shows how to use this tool to generate the classes for the [Transport: UDP](transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="86e79-111">So führen Sie das Tool aus</span><span class="sxs-lookup"><span data-stu-id="86e79-111">To run the tool</span></span>  
  
1. <span data-ttu-id="86e79-112">Wenn Sie sowohl einen benutzerdefinierten `BindingElement`-Typ als auch einen benutzerdefinierten `Binding`-Typ haben, geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86e79-112">At the command prompt type the following if you have both a custom `BindingElement` type and a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     <span data-ttu-id="86e79-113">Wenn Sie nur einen benutzerdefinierten `BindingElement`-Typ haben, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86e79-113">Or type the following if you have only a custom `BindingElement` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="86e79-114">Wenn Sie nur einen benutzerdefinierten `Binding`-Typ haben, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86e79-114">Or type the following if you have only a custom `Binding` type:</span></span>  
  
    ```console  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="86e79-115">Der Befehl generiert drei .cs-Dateien für das `BindingElement` (wenn sie die Option "/be:" angegeben haben), fünf .cs-Dateien für die normale `Binding` (wenn Sie die Option "/sb:" angegeben haben), und eine .xml-Datei.</span><span class="sxs-lookup"><span data-stu-id="86e79-115">The command generates three .cs files for the `BindingElement` (if you specified the /be: option), five .cs files for the standard `Binding` (if you specified the /sb: option), and a .xml file.</span></span>  
  
    1. <span data-ttu-id="86e79-116">Bei Verwendung der Option "/be" implementiert eine der .cs-Dateien den `BindingElementExtensionSection` für Ihr Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="86e79-116">If you used the /be option, one of the .cs files implements the `BindingElementExtensionSection` for your binding element.</span></span> <span data-ttu-id="86e79-117">Dieser Code macht Ihr `BindingElement` für das Konfigurationssystem verfügbar, sodass Ihr Bindungselement auch von anderen benutzerdefinierten Bindungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="86e79-117">This code exposes your `BindingElement` to the configuration system, so that other custom bindings can use your binding element.</span></span> <span data-ttu-id="86e79-118">Die anderen Dateien enthalten Klassen, die Standardwerte und Konstanten darstellen.</span><span class="sxs-lookup"><span data-stu-id="86e79-118">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="86e79-119">Die Dateien enthalten `//TODO`-Kommentare, um Sie daran zu erinnern, die Standardwerte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="86e79-119">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
    2. <span data-ttu-id="86e79-120">Wenn Sie die Option „/sb“ angegeben haben, implementieren zwei der „.cs“-Dateien ein `StandardBindingElement` bzw. ein `StandardBindingCollectionElement`, das Ihre Standardbindung für das Konfigurationssystem verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="86e79-120">If you specified the /sb option, two of the .cs files implement a `StandardBindingElement` and a `StandardBindingCollectionElement` respectively, which exposes your standard binding to the configuration system.</span></span> <span data-ttu-id="86e79-121">Die anderen Dateien enthalten Klassen, die Standardwerte und Konstanten darstellen.</span><span class="sxs-lookup"><span data-stu-id="86e79-121">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="86e79-122">Die Dateien enthalten `//TODO`-Kommentare, um Sie daran zu erinnern, die Standardwerte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="86e79-122">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
         <span data-ttu-id="86e79-123">Wenn Sie die Option "/SB: angegeben haben, verfügt CodeToAddTo \<*YourStdBinding*> . cs über Code, den Sie manuell der Klasse hinzufügen müssen, die Ihre Standard Bindung implementiert.</span><span class="sxs-lookup"><span data-stu-id="86e79-123">If you specified the /sb: option the CodeToAddTo\<*YourStdBinding*>.cs has code that you must manually add into the class that implements your standard binding.</span></span>  
  
     <span data-ttu-id="86e79-124">Die Datei "SampleConfig.xml" enthält den Konfigurationscode, den Sie der Konfigurationsdatei hinzufügen müssen, die die oben in Schritt 1 oder 2 definierten Handler registriert.</span><span class="sxs-lookup"><span data-stu-id="86e79-124">The SampleConfig.xml file contains the configuration code that you must add to the configuration file that registers the handlers defined in the previous step 1 or 2.</span></span>  

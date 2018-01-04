---
title: Auftragsverarbeitung mit Richtlinie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d86c7890af651ba9f0ee0ec2a1763f9c579bac89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="order-processing-with-policy"></a><span data-ttu-id="39400-102">Auftragsverarbeitung mit Richtlinie</span><span class="sxs-lookup"><span data-stu-id="39400-102">Order Processing with Policy</span></span>
<span data-ttu-id="39400-103">Das Beispiel Auftragsverarbeitungsrichtlinie veranschaulicht einige der in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] von Windows Workflow Foundation (WF) eingeführten Schlüsselfeatures.</span><span class="sxs-lookup"><span data-stu-id="39400-103">The Order Processing Policy sample demonstrates some of the key features introduced in the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] of the Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="39400-104">Die folgende Funktionalität ist für das WF-Regelmodul neu:</span><span class="sxs-lookup"><span data-stu-id="39400-104">The following functionality is new for the WF rules engine:</span></span>  
  
-   <span data-ttu-id="39400-105">Unterstützung für Operatorüberladung.</span><span class="sxs-lookup"><span data-stu-id="39400-105">Support for operator overloading.</span></span>  
  
-   <span data-ttu-id="39400-106">Unterstützung für den `new`-Operator, mit dem die Benutzer neue Objekte und Arrays von WF-Regeln erstellen können.</span><span class="sxs-lookup"><span data-stu-id="39400-106">Support for the `new` operator, allowing users to create new objects and arrays from WF rules.</span></span>  
  
-   <span data-ttu-id="39400-107">Unterstützung von Erweiterungsmethoden, um die Benutzerfreundlichkeit beim Aufrufen der Erweiterungsmethoden von WF-Regeln mit den C#-Codierungsstilen kompatibel zu machen.</span><span class="sxs-lookup"><span data-stu-id="39400-107">Support for extension methods to make the user experience in calling extension methods from WF rules compatible with C# coding styles.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39400-108">Für dieses Beispiel ist es erforderlich, dass [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] für die Erstellung und Ausführung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="39400-108">This sample requires that [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] is installed to build and run.</span></span> [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]<span data-ttu-id="39400-109"> ist erforderlich, um die Projekt- und Projektmappendateien zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="39400-109"> is required to open the project and solution files.</span></span>  
  
 <span data-ttu-id="39400-110">Das Beispiel veranschaulicht ein `OrderProcessingPolicy`-Projekt, in dem eine Kundenbestellung eingegeben wird, die aus einer nummerierten Liste mit verfügbaren Elementen und einer Postleitzahl besteht.</span><span class="sxs-lookup"><span data-stu-id="39400-110">The sample demonstrates an `OrderProcessingPolicy` project in which a customer order, which consists of a numbered list of available items and a zip code, is entered.</span></span> <span data-ttu-id="39400-111">Die Bestellung wird erfolgreich verarbeitet, wenn beide Einträge richtig sind. Andernfalls erstellt die Richtlinie Fehlerobjekte, wobei ein überladener `+`-Operator sowie eine vordefinierte Erweiterungsmethode verwendet werden, um den Benutzer über die Fehler zu informieren.</span><span class="sxs-lookup"><span data-stu-id="39400-111">The order is processed successfully if both entries are correct; otherwise, the policy creates error objects, utilizing an overloaded `+` operator and a predefined extension method to inform the user of the errors.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="39400-112">Erweiterungsmethoden [c#], finden Sie unter [c# Version 3.0-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=95402).</span><span class="sxs-lookup"><span data-stu-id="39400-112"> extension methods, see [C# Version 3.0 Specification](http://go.microsoft.com/fwlink/?LinkId=95402).</span></span>  
  
 <span data-ttu-id="39400-113">Das Beispiel besteht aus den folgenden Projekten:</span><span class="sxs-lookup"><span data-stu-id="39400-113">The sample is comprised of the following projects:</span></span>  
  
-   `OrderErrorLibrary`  
  
     <span data-ttu-id="39400-114">`OrderErrorLibrary` ist eine Klassenbibliothek, mit der die `OrderError`-Klasse und die `OrderErrorCollection`-Klasse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="39400-114">The `OrderErrorLibrary` is a class library that defines `OrderError` and `OrderErrorCollection` classes.</span></span> <span data-ttu-id="39400-115">Eine `OrderError`-Instanz wird erstellt, wenn eine ungültige Eingabe gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="39400-115">An `OrderError` instance is created when an invalid input is entered.</span></span> <span data-ttu-id="39400-116">Die Bibliothek bietet auch eine Erweiterungsmethode in der `OrderErrorCollection`-Klasse, mit der die `ErrorText`-Eigenschaft für alle `OrderError`-Objekte in der `OrderErrorCollection` ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="39400-116">The library also provides an extension method on the `OrderErrorCollection` class that outputs the `ErrorText` property on all `OrderError` objects in the `OrderErrorCollection`.</span></span>  
  
-   `OrderProcessingPolicy`  
  
     <span data-ttu-id="39400-117">Das `OrderProcessingPolicy`-Projekt ist eine WF-Konsolenanwendung, die eine einzelne `PolicyFromFile`-Aktivität definiert.</span><span class="sxs-lookup"><span data-stu-id="39400-117">The `OrderProcessingPolicy` project is a WF console application that defines a single `PolicyFromFile` activity.</span></span> <span data-ttu-id="39400-118">Die Aktivität weist folgende Regeln auf:</span><span class="sxs-lookup"><span data-stu-id="39400-118">The activity has the following rules:</span></span>  
  
    -   `invalidItemNum`  
  
         <span data-ttu-id="39400-119">Diese Regel überprüft, dass die Artikelnummer zwischen 1 und 6 liegt.</span><span class="sxs-lookup"><span data-stu-id="39400-119">This rule validates that the item number is between 1 and 6, inclusive.</span></span> <span data-ttu-id="39400-120">Wenn die Artikelnummer innerhalb des gültigen Bereichs liegt, führt die Regel keine Aktion aus (mit Ausnahme des Druckens auf der Konsole).</span><span class="sxs-lookup"><span data-stu-id="39400-120">If the item number is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="39400-121">Wenn die Artikelnummer nicht zwischen 1 und 6 liegt, geht die `invalidItemNum`-Regel wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="39400-121">If the item number is not between 1 and 6, the `invalidItemNum` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="39400-122">Sie erstellt ein neues `OrderError`-Objekt und übergibt ihm die eingegebene Artikelnummer. Außerdem legt sie die `ErrorText`-Eigenschaft und die `CustomerName`-Eigenschaft für das Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="39400-122">Creates a new `OrderError` object, passing it the item number entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="39400-123">Sie erstellt ein `invalidItemNumErrorCollection`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="39400-123">Creates an `invalidItemNumErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="39400-124">Sie fügt die neu erstellte `OrderError`-Instanz der `invalidItemNumErrorCollection` hinzu.</span><span class="sxs-lookup"><span data-stu-id="39400-124">Adds the newly-created `OrderError` instance to the `invalidItemNumErrorCollection`.</span></span>  
  
         <span data-ttu-id="39400-125">Dies weist auf die Unterstützung des `new`-Operators hin, mit dem Objekte in Regeln instanziiert werden können.</span><span class="sxs-lookup"><span data-stu-id="39400-125">This demonstrates support for the `new` operator, with which you can instantiate objects inside rules.</span></span>  
  
    -   `invalidZip`  
  
         <span data-ttu-id="39400-126">Diese Regel überprüft, ob die Postleitzahl 5 Ziffern hat und im Bereich 600 bis 99998 liegt.</span><span class="sxs-lookup"><span data-stu-id="39400-126">This rule validates that the zip code has 5 digits, and is within the range 600 to 99998.</span></span> <span data-ttu-id="39400-127">Wenn die Postleitzahl innerhalb des gültigen Bereichs liegt, führt die Regel keine Aktion aus (mit Ausnahme der Ausgabe auf der Konsole).</span><span class="sxs-lookup"><span data-stu-id="39400-127">If the zip code is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="39400-128">Falls die Postleitzahl weniger als 5 Stellen aufweist oder nicht im Bereich 00600 bis 99998 liegt, geht die `invalidZip`-Regel wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="39400-128">If the length of the zip code is less than 5, or the zip code is not between 00600 and 99998, the `invalidZip` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="39400-129">Sie erstellt ein `OrderError`-Objekt und übergibt ihm die eingegebene Postleitzahl. Außerdem legt sie die `ErrorText`-Eigenschaft und die `CustomerName`-Eigenschaft für das Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="39400-129">Creates an `OrderError` object, passing it the zip code entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="39400-130">Sie erstellt ein `invalidZipCodeErrorCollection`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="39400-130">Creates an `invalidZipCodeErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="39400-131">Sie fügt die neu erstellte `OrderError`-Instanz der neu erstellten `invalidZipCodeErrorCollection` hinzu.</span><span class="sxs-lookup"><span data-stu-id="39400-131">Adds the newly-created `OrderError` instance to the newly-created `invalidZipCodeErrorCollection`.</span></span>  
  
         <span data-ttu-id="39400-132">Diese Regel veranschaulicht die Unterstützung des `new`-Operators, mit dem Objekte in Regeln instanziiert werden können.</span><span class="sxs-lookup"><span data-stu-id="39400-132">This rule again demonstrates support for the `new` operator, which allows you to instantiate objects inside rules.</span></span>  
  
    -   `displayErrors`  
  
         <span data-ttu-id="39400-133">Bei dieser Regel wird überprüft, ob von den vorherigen beiden Regeln in den beiden `OrderErrorCollection`-Objekten `invalidItemNumErrorCollection` und `invalidIZipCodeErrorCollection` Fehler hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="39400-133">This rule checks to see if there were any errors added by the previous two rules in the two `OrderErrorCollection` objects `invalidItemNumErrorCollection` and `invalidIZipCodeErrorCollection`.</span></span> <span data-ttu-id="39400-134">Wenn es Fehler (entweder die `invalidItemNumErrorCollection` oder die `invalidZipCodeErrorCollection` ist nicht `null`) gegeben hat, geht die Regel wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="39400-134">If there were errors (either `invalidItemNumErrorCollection` or `invalidZipCodeErrorCollection` is not `null`), the rule does the following:</span></span>  
  
        1.  <span data-ttu-id="39400-135">Ruft den überladenen `+` -Operator zum Kopieren des Inhalts der `invalidItemNumErrorCollection` und `invalidZipCodeErrorCollection` auf eine `invalidOrdersCollection``OrderErrorCollection` Instanz.</span><span class="sxs-lookup"><span data-stu-id="39400-135">Calls the overloaded `+` operator to copy the contents of `invalidItemNumErrorCollection` and `invalidZipCodeErrorCollection` to an `invalidOrdersCollection``OrderErrorCollection` instance.</span></span>  
  
        2.  <span data-ttu-id="39400-136">Sie ruft die `PrintOrderErrors`-Erweiterungsmethode für die `invalidOrdersCollection` auf und gibt die `ErrorText`-Eigenschaft für alle `orderError`-Objekte in der `invalidOrdersCollection` aus.</span><span class="sxs-lookup"><span data-stu-id="39400-136">Calls the `PrintOrderErrors` extension method on `invalidOrdersCollection` and outputs the `ErrorText` property on all `orderError` objects in `invalidOrdersCollection`.</span></span>  
  
 <span data-ttu-id="39400-137">Der überladene `+`-Operator der `OrderErrorCollection` wird in der `OrderErrorCollection`-Klasse im `OrderErrorLibrary`-Projekt definiert.</span><span class="sxs-lookup"><span data-stu-id="39400-137">The overloaded operator `+` on the `OrderErrorCollection` is defined in the `OrderErrorCollection` class, in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="39400-138">Er verfügt über zwei `OrderErrorCollection`-Objekte und kombiniert diese in einem `OrderErrorCollection`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="39400-138">It takes two `OrderErrorCollection` objects and combines them into one `OrderErrorCollection` object.</span></span>  
  
 <span data-ttu-id="39400-139">Die `PrintOrderErrors`-Erweiterungsmethode wird auch im `OrderErrorLibrary`-Projekt definiert.</span><span class="sxs-lookup"><span data-stu-id="39400-139">The `PrintOrderErrors` extension method is also defined in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="39400-140">Erweiterungsmethoden sind ein neues C#-Feature, mit dem Entwickler dem öffentlichen Vertrag eines vorhandenen CLR-Typs neue Methoden hinzufügen können, ohne davon eine Klasse ableiten oder den ursprünglichen Typ neu kompilieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="39400-140">Extension methods are a new C# feature that enables developers to add new methods to the public contract of an existing CLR type, without having to derive a class from it or recompile the original type.</span></span>  
  
 <span data-ttu-id="39400-141">Beim Ausführen eines Beispiels werden Sie zur Eingabe eines Namens, der Artikelnummer des zu erwerbenden Artikels und einer Postleitzahl aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="39400-141">When you run the sample you are prompted to enter a name, the item number of the item to be purchased, and a zip code.</span></span> <span data-ttu-id="39400-142">Diese Informationen werden dann von den in der Richtlinienaktivität definierten Regeln überprüft.</span><span class="sxs-lookup"><span data-stu-id="39400-142">This information is then verified by the rules defined in the policy activity.</span></span> <span data-ttu-id="39400-143">Im Folgenden finden Sie eine Beispielausgabe des Programms.</span><span class="sxs-lookup"><span data-stu-id="39400-143">The following is sample output from the program.</span></span>  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="39400-144">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="39400-144">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="39400-145">Öffnen Sie die Projektdatei OrderProcessingPolicy.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39400-145">Open the OrderProcessingPolicy.sln project file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="39400-146">Es gibt zwei verschiedene Projekte in der Projektmappe: `OrderErrorLibrary` und `OrderProcessingPolicy`.</span><span class="sxs-lookup"><span data-stu-id="39400-146">There are two different projects in the solution: `OrderErrorLibrary` and `OrderProcessingPolicy`.</span></span> <span data-ttu-id="39400-147">Das `OrderProcessingPolicy`-Projekt verwendet in der `OrderErrorLibrary` definierte Klassen und Methoden.</span><span class="sxs-lookup"><span data-stu-id="39400-147">The `OrderProcessingPolicy` project uses classes and methods defined in the `OrderErrorLibrary`.</span></span>  
  
3.  <span data-ttu-id="39400-148">Erstellen Sie alle Projekte.</span><span class="sxs-lookup"><span data-stu-id="39400-148">Build all projects.</span></span>  
  
4.  <span data-ttu-id="39400-149">Klicken Sie auf **ausführen**.</span><span class="sxs-lookup"><span data-stu-id="39400-149">Click **Run**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="39400-150">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="39400-150">The samples may already be installed on your computer.</span></span> <span data-ttu-id="39400-151">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="39400-151">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="39400-152">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="39400-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="39400-153">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="39400-153">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`
---
title: 'Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dba117ac9f4fd7dc745019d9705c2a707a5b526c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="91a26-102">Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="91a26-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="91a26-103">Aktivieren Sie zum automatischen Generieren von clientdatendienstklassen bei Verwendung von Visual Studio integriert die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio-Projekt einen Verweis auf einen Datendienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="91a26-103"> integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="91a26-104">Weitere Informationen finden Sie unter [wie: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="91a26-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="91a26-105">Sie können auch die gleichen Clientdatendienstklassen mit dem Tool zur Codeerstellung `DataSvcUtil.exe` manuell generieren.</span><span class="sxs-lookup"><span data-stu-id="91a26-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="91a26-106">Dieses Tool, das in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthalten ist, generiert aus der Datendienstdefinition .NET Framework-Klassen.</span><span class="sxs-lookup"><span data-stu-id="91a26-106">This tool, which is included with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="91a26-107">Es kann auch verwendet werden, um Datendienstklassen aus der Konzeptmodelldatei (CSDL) und der EDMX-Datei zu generieren, die ein Entity Framework-Modell in einem Visual Studio-Projekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="91a26-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>  
  
 <span data-ttu-id="91a26-108">Im Beispiel in diesem Thema werden Clientdatendienstklassen basierend auf dem Northwind-Beispieldatendienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="91a26-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="91a26-109">Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="91a26-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="91a26-110">Für einige Beispiele in diesem Thema ist die Konzeptmodelldatei für das Northwind-Modell erforderlich.</span><span class="sxs-lookup"><span data-stu-id="91a26-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="91a26-111">Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="91a26-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="91a26-112">Für einige Beispiele in diesem Thema ist die EDMX-Datei für das Northwind-Modell erforderlich.</span><span class="sxs-lookup"><span data-stu-id="91a26-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="91a26-113">Weitere Informationen finden Sie unter [EDMX-Datei (Übersicht)](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span><span class="sxs-lookup"><span data-stu-id="91a26-113">For more information, see [.edmx File Overview](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span></span>  
  
### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="91a26-114">So erstellen Sie C#-Klassen, die die Datenbindung unterstützen</span><span class="sxs-lookup"><span data-stu-id="91a26-114">To generate C# classes that support data binding</span></span>  
  
-   <span data-ttu-id="91a26-115">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="91a26-116">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="91a26-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="91a26-117">So erstellen Sie Visual Basic-Klassen, die die Datenbindung unterstützen</span><span class="sxs-lookup"><span data-stu-id="91a26-117">To generate Visual Basic classes that support data binding</span></span>  
  
-   <span data-ttu-id="91a26-118">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-118">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="91a26-119">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="91a26-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="91a26-120">So erstellen Sie C#-Klassen basierend auf dem Dienst-URI</span><span class="sxs-lookup"><span data-stu-id="91a26-120">To generate C# classes based on the service URI</span></span>  
  
-   <span data-ttu-id="91a26-121">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-121">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="91a26-122">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="91a26-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="91a26-123">So erstellen Sie Visual Basic-Klassen basierend auf dem Dienst-URI</span><span class="sxs-lookup"><span data-stu-id="91a26-123">To generate Visual Basic classes based on the service URI</span></span>  
  
-   <span data-ttu-id="91a26-124">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-124">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="91a26-125">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="91a26-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="91a26-126">So erstellen Sie C#-Klassen basierend auf der Konzeptmodelldatei (CSDL)</span><span class="sxs-lookup"><span data-stu-id="91a26-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="91a26-127">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-127">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="91a26-128">So erstellen Sie Visual Basic-Klassen basierend auf der Konzeptmodelldatei (CSDL)</span><span class="sxs-lookup"><span data-stu-id="91a26-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="91a26-129">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-129">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="91a26-130">So erstellen Sie C#-Klassen basierend auf der EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="91a26-130">To generate C# classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="91a26-131">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-131">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="91a26-132">So erstellen Sie Visual Basic-Klassen basierend auf der EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="91a26-132">To generate Visual Basic classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="91a26-133">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="91a26-133">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="91a26-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91a26-134">See Also</span></span>  
 [<span data-ttu-id="91a26-135">Generieren der Datendienst-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="91a26-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [<span data-ttu-id="91a26-136">Vorgehensweise: Hinzufügen eines Datendienstverweises</span><span class="sxs-lookup"><span data-stu-id="91a26-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)  
 [<span data-ttu-id="91a26-137">WCF Data Service-Clienthilfsprogramm („DataSvcUtil.exe“)</span><span class="sxs-lookup"><span data-stu-id="91a26-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)

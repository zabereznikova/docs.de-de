---
title: 'Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 332c04f50e104a5e1c8bd18c05581b6c0472f82f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501320"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="28949-102">Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="28949-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="28949-103">WCF Data Services-Integration mit Visual Studio können Sie Client-Datendienstklassen automatisch zu generieren, bei der Verwendung der **Hinzufügen eines Dienstverweises** einen Verweis auf einen Datendienst in einem Visual Studio-Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="28949-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="28949-104">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28949-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="28949-105">Sie können auch die gleichen Clientdatendienstklassen mit dem Tool zur Codeerstellung `DataSvcUtil.exe` manuell generieren.</span><span class="sxs-lookup"><span data-stu-id="28949-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="28949-106">Dieses Tool, das in WCF Data Services enthalten ist, generiert .NET Framework-Klassen aus der Datendienstdefinition.</span><span class="sxs-lookup"><span data-stu-id="28949-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="28949-107">Es kann auch verwendet werden, um Datendienstklassen aus der Konzeptmodelldatei (CSDL) und der EDMX-Datei zu generieren, die ein Entity Framework-Modell in einem Visual Studio-Projekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="28949-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="28949-108">Im Beispiel in diesem Thema werden Clientdatendienstklassen basierend auf dem Northwind-Beispieldatendienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="28949-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="28949-109">Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="28949-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="28949-110">Für einige Beispiele in diesem Thema ist die Konzeptmodelldatei für das Northwind-Modell erforderlich.</span><span class="sxs-lookup"><span data-stu-id="28949-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="28949-111">Weitere Informationen finden Sie unter [wie: Generieren Sie das Modell und die Mapping-Dateien mithilfe von EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="28949-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="28949-112">Für einige Beispiele in diesem Thema ist die EDMX-Datei für das Northwind-Modell erforderlich.</span><span class="sxs-lookup"><span data-stu-id="28949-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="28949-113">Weitere Informationen finden Sie unter [EDMX-Datei Übersicht](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span><span class="sxs-lookup"><span data-stu-id="28949-113">For more information, see [.edmx File Overview](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="28949-114">So erstellen Sie C#-Klassen, die die Datenbindung unterstützen</span><span class="sxs-lookup"><span data-stu-id="28949-114">To generate C# classes that support data binding</span></span>

-   <span data-ttu-id="28949-115">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="28949-116">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="28949-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="28949-117">So erstellen Sie Visual Basic-Klassen, die die Datenbindung unterstützen</span><span class="sxs-lookup"><span data-stu-id="28949-117">To generate Visual Basic classes that support data binding</span></span>

-   <span data-ttu-id="28949-118">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="28949-119">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="28949-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="28949-120">So erstellen Sie C#-Klassen basierend auf dem Dienst-URI</span><span class="sxs-lookup"><span data-stu-id="28949-120">To generate C# classes based on the service URI</span></span>

-   <span data-ttu-id="28949-121">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="28949-122">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="28949-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="28949-123">So erstellen Sie Visual Basic-Klassen basierend auf dem Dienst-URI</span><span class="sxs-lookup"><span data-stu-id="28949-123">To generate Visual Basic classes based on the service URI</span></span>

-   <span data-ttu-id="28949-124">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="28949-125">Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.</span><span class="sxs-lookup"><span data-stu-id="28949-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="28949-126">So erstellen Sie C#-Klassen basierend auf der Konzeptmodelldatei (CSDL)</span><span class="sxs-lookup"><span data-stu-id="28949-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

-   <span data-ttu-id="28949-127">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="28949-128">So erstellen Sie Visual Basic-Klassen basierend auf der Konzeptmodelldatei (CSDL)</span><span class="sxs-lookup"><span data-stu-id="28949-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

-   <span data-ttu-id="28949-129">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="28949-130">So erstellen Sie C#-Klassen basierend auf der EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="28949-130">To generate C# classes based on the .edmx file</span></span>

-   <span data-ttu-id="28949-131">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="28949-132">So erstellen Sie Visual Basic-Klassen basierend auf der EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="28949-132">To generate Visual Basic classes based on the .edmx file</span></span>

-   <span data-ttu-id="28949-133">Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:</span><span class="sxs-lookup"><span data-stu-id="28949-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="28949-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28949-134">See Also</span></span>

- [<span data-ttu-id="28949-135">Generieren der Datendienst-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="28949-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="28949-136">Vorgehensweise: Hinzufügen eines Datendienstverweises</span><span class="sxs-lookup"><span data-stu-id="28949-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="28949-137">WCF Data Service-Clienthilfsprogramm („DataSvcUtil.exe“)</span><span class="sxs-lookup"><span data-stu-id="28949-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
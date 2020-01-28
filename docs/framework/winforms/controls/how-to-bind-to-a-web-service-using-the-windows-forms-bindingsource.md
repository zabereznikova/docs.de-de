---
title: Binden an einen Webdienst mithilfe von BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
ms.openlocfilehash: 0680c73e578577cf40158761f6c635fe30ff9f4d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746681"
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="bfd64-102">Gewusst wie: Binden an einen Webdienst mithilfe der BindingSource in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bfd64-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="bfd64-103">Wenn Sie ein Windows Form-Steuerelements an die Ergebnisse des Aufrufs eines XML-Webdiensts binden möchten, können Sie eine <xref:System.Windows.Forms.BindingSource>-Komponente verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfd64-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="bfd64-104">Dieses Verfahren ähnelt der Bindung einer <xref:System.Windows.Forms.BindingSource>-Komponente an einen Typ.</span><span class="sxs-lookup"><span data-stu-id="bfd64-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="bfd64-105">Sie müssen einen clientseitigen Proxy erstellen, der die Methoden und Typen enthält, die vom Webdienst bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bfd64-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="bfd64-106">Sie generieren einen clientseitigen Proxy über den Webdienst (.asmx) selbst oder über seine WSDL-Datei (Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="bfd64-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="bfd64-107">Darüber hinaus muss der clientseitige Proxy die Felder von komplexen Typen verfügbar machen, die vom Webdienst als öffentliche Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bfd64-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="bfd64-108">Anschließend binden Sie <xref:System.Windows.Forms.BindingSource> an einen der im Webdienstproxy bereitgestellten Typen.</span><span class="sxs-lookup"><span data-stu-id="bfd64-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="bfd64-109">So erstellen und binden Sie einen clientseitigen Proxy</span><span class="sxs-lookup"><span data-stu-id="bfd64-109">To create and bind to a client-side proxy</span></span>  
  
1. <span data-ttu-id="bfd64-110">Erstellen Sie ein Windows Form mit einem geeigneten Namespace im gewünschten Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bfd64-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2. <span data-ttu-id="bfd64-111">Fügen Sie eine <xref:System.Windows.Forms.BindingSource>-Komponente zum Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfd64-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3. <span data-ttu-id="bfd64-112">Öffnen Sie die Windows Software Development Kit (SDK)-Eingabeaufforderung, und navigieren Sie zu demselben Verzeichnis, in dem sich das Formular befindet.</span><span class="sxs-lookup"><span data-stu-id="bfd64-112">Open the Windows Software Development Kit (SDK) command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4. <span data-ttu-id="bfd64-113">Geben Sie mithilfe des WSDL-Tools `wsdl` und die URL für die ASMX- oder WSDL-Datei für den Webdienst gefolgt vom Namespace der Anwendung und wahlweise der verwendeten Programmiersprache ein.</span><span class="sxs-lookup"><span data-stu-id="bfd64-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="bfd64-114">Im folgenden Codebeispiel wird der-Webdienst unter `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfd64-114">The following code example uses the Web service located at `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`.</span></span> <span data-ttu-id="bfd64-115">Geben Sie z.B. für C# `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` oder für Visual Basic `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB` ein.</span><span class="sxs-lookup"><span data-stu-id="bfd64-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="bfd64-116">Durch die Übergabe des Pfads als Argument an das WSDL-Tool wird ein clientseitiger Proxy in demselben Verzeichnis und Namespace wie Ihre Anwendung sowie in der angegebenen Sprache generiert.</span><span class="sxs-lookup"><span data-stu-id="bfd64-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="bfd64-117">Wenn Sie Visual Studio verwenden, fügen Sie die Datei Ihrem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfd64-117">If you are using Visual Studio, add the file to your project.</span></span>  
  
5. <span data-ttu-id="bfd64-118">Wählen Sie im clientseitigen Proxy einen Typ für die Bindung aus.</span><span class="sxs-lookup"><span data-stu-id="bfd64-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="bfd64-119">Dies ist normalerweise ein Typ, der von einer vom Webdienst angebotenen Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bfd64-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="bfd64-120">Die Felder des ausgewählten Typs müssen zu Bindungszwecken als öffentliche Eigenschaften verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="bfd64-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6. <span data-ttu-id="bfd64-121">Legen Sie für die <xref:System.Windows.Forms.BindingSource.DataSource%2A>-Eigenschaft von <xref:System.Windows.Forms.BindingSource> den gewünschten Typ fest, der im clientseitigen Proxy des Webdiensts enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="bfd64-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="bfd64-122">So binden Sie Steuerelemente an die Bindungsquelle, die an einen Webdienst gebunden ist</span><span class="sxs-lookup"><span data-stu-id="bfd64-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
- <span data-ttu-id="bfd64-123">Binden Sie Steuerelemente an <xref:System.Windows.Forms.BindingSource>, wobei Sie die öffentliche Eigenschaft des Webdiensttyps übergeben, den Sie als Parameter verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bfd64-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="bfd64-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bfd64-124">Example</span></span>  
 <span data-ttu-id="bfd64-125">Das folgende Codebeispiel veranschaulicht das Binden einer <xref:System.Windows.Forms.BindingSource>-Komponente an einen Webdienst und das anschließende Binden eines Textfelds an die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="bfd64-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="bfd64-126">Wenn Sie auf die Schaltfläche klicken, wird eine Webdienstmethode aufgerufen und die Ergebnisse werden in `textbox1` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bfd64-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bfd64-127">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bfd64-127">Compiling the Code</span></span>  
 <span data-ttu-id="bfd64-128">Dies ist ein vollständiges Beispiel, das eine `Main`-Methode und eine verkürzte Version des clientseitigen Proxycodes enthält.</span><span class="sxs-lookup"><span data-stu-id="bfd64-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="bfd64-129">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bfd64-129">This example requires:</span></span>  
  
- <span data-ttu-id="bfd64-130">Verweise auf die Assemblys "System", "System.Drawing", "System.Web.Services", "System.Windows.Forms" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="bfd64-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd64-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfd64-131">See also</span></span>

- [<span data-ttu-id="bfd64-132">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="bfd64-132">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="bfd64-133">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="bfd64-133">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)

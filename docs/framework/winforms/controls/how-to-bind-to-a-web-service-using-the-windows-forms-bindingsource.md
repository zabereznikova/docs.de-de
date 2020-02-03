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
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a>Gewusst wie: Binden an einen Webdienst mithilfe der BindingSource in Windows Forms
Wenn Sie ein Windows Form-Steuerelements an die Ergebnisse des Aufrufs eines XML-Webdiensts binden möchten, können Sie eine <xref:System.Windows.Forms.BindingSource>-Komponente verwenden. Dieses Verfahren ähnelt der Bindung einer <xref:System.Windows.Forms.BindingSource>-Komponente an einen Typ. Sie müssen einen clientseitigen Proxy erstellen, der die Methoden und Typen enthält, die vom Webdienst bereitgestellt werden. Sie generieren einen clientseitigen Proxy über den Webdienst (.asmx) selbst oder über seine WSDL-Datei (Web Services Description Language). Darüber hinaus muss der clientseitige Proxy die Felder von komplexen Typen verfügbar machen, die vom Webdienst als öffentliche Eigenschaften verwendet werden. Anschließend binden Sie <xref:System.Windows.Forms.BindingSource> an einen der im Webdienstproxy bereitgestellten Typen.  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a>So erstellen und binden Sie einen clientseitigen Proxy  
  
1. Erstellen Sie ein Windows Form mit einem geeigneten Namespace im gewünschten Verzeichnis.  
  
2. Fügen Sie eine <xref:System.Windows.Forms.BindingSource>-Komponente zum Formular hinzu.  
  
3. Öffnen Sie die Windows Software Development Kit (SDK)-Eingabeaufforderung, und navigieren Sie zu demselben Verzeichnis, in dem sich das Formular befindet.  
  
4. Geben Sie mithilfe des WSDL-Tools `wsdl` und die URL für die ASMX- oder WSDL-Datei für den Webdienst gefolgt vom Namespace der Anwendung und wahlweise der verwendeten Programmiersprache ein.  
  
     Im folgenden Codebeispiel wird der-Webdienst unter `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`verwendet. Geben Sie z.B. für C# `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` oder für Visual Basic `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB` ein. Durch die Übergabe des Pfads als Argument an das WSDL-Tool wird ein clientseitiger Proxy in demselben Verzeichnis und Namespace wie Ihre Anwendung sowie in der angegebenen Sprache generiert. Wenn Sie Visual Studio verwenden, fügen Sie die Datei Ihrem Projekt hinzu.  
  
5. Wählen Sie im clientseitigen Proxy einen Typ für die Bindung aus.  
  
     Dies ist normalerweise ein Typ, der von einer vom Webdienst angebotenen Methode zurückgegeben wird. Die Felder des ausgewählten Typs müssen zu Bindungszwecken als öffentliche Eigenschaften verfügbar gemacht werden.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6. Legen Sie für die <xref:System.Windows.Forms.BindingSource.DataSource%2A>-Eigenschaft von <xref:System.Windows.Forms.BindingSource> den gewünschten Typ fest, der im clientseitigen Proxy des Webdiensts enthalten ist.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a>So binden Sie Steuerelemente an die Bindungsquelle, die an einen Webdienst gebunden ist  
  
- Binden Sie Steuerelemente an <xref:System.Windows.Forms.BindingSource>, wobei Sie die öffentliche Eigenschaft des Webdiensttyps übergeben, den Sie als Parameter verwenden möchten.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht das Binden einer <xref:System.Windows.Forms.BindingSource>-Komponente an einen Webdienst und das anschließende Binden eines Textfelds an die <xref:System.Windows.Forms.BindingSource>-Komponente. Wenn Sie auf die Schaltfläche klicken, wird eine Webdienstmethode aufgerufen und die Ergebnisse werden in `textbox1` angezeigt.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dies ist ein vollständiges Beispiel, das eine `Main`-Methode und eine verkürzte Version des clientseitigen Proxycodes enthält.  
  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Drawing", "System.Web.Services", "System.Windows.Forms" und "System.Xml".  
  
## <a name="see-also"></a>Weitere Informationen

- [BindingSource-Komponente](bindingsource-component.md)
- [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md)

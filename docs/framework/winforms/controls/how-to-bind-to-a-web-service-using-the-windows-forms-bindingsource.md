---
title: "Gewusst wie: Binden an einen Webdienst mithilfe der BindingSource in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingSource-Komponente [Windows Forms], Binden an einen Webdienst"
  - "BindingSource-Komponente [Windows Forms], Beispiele"
  - "Steuerelemente [Windows Forms], Binden an einen Webdienst"
  - "Beispiele [Windows Forms], BindingSource-Komponente"
  - "Webdienste, Binden von Steuerelementen"
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Gewusst wie: Binden an einen Webdienst mithilfe der BindingSource in Windows Forms
Wenn Sie ein Windows Form\-Steuerelements an die Ergebnisse des Aufrufs eines XML\-Webdiensts binden möchten, können Sie eine <xref:System.Windows.Forms.BindingSource>\-Komponente verwenden.  Dieses Verfahren ähnelt der Bindung einer <xref:System.Windows.Forms.BindingSource>\-Komponente an einen Typ.  Sie müssen einen clientseitigen Proxy erstellen, der die Methoden und Typen enthält, die vom Webdienst bereitgestellt werden.  Sie generieren einen clientseitigen Proxy über den Webdienst \(.asmx\) selbst oder über seine WSDL\-Datei \(Web Services Description Language\).  Darüber hinaus muss der clientseitige Proxy die Felder von komplexen Typen verfügbar machen, die vom Webdienst als öffentliche Eigenschaften verwendet werden.  Anschließend binden Sie <xref:System.Windows.Forms.BindingSource> an einen der im Webdienstproxy bereitgestellten Typen.  
  
### So erstellen und binden Sie einen clientseitigen Proxy  
  
1.  Erstellen Sie ein Windows Form mit einem geeigneten Namespace im gewünschten Verzeichnis.  
  
2.  Fügen Sie eine <xref:System.Windows.Forms.BindingSource>\-Komponente zum Formular hinzu.  
  
3.  Öffnen Sie die [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)]\-Eingabeaufforderung, und navigieren Sie zu demselben Verzeichnis, in dem sich Ihr Formular befindet.  
  
4.  Geben Sie mithilfe des WSDL\-Tools `wsdl` und die URL für die ASMX\- oder WSDL\-Datei für den Webdienst gefolgt vom Namespace der Anwendung und wahlweise der verwendeten Programmiersprache ein.  
  
     Das folgende Codebeispiel verwendet den Webdienst unter "http:\/\/webservices.eraserver".  net\/zipcoderesolver\/zipcoderesolver.asmx.  Beispiel: Geben Sie für C\# `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` oder für Visual Basic `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB` ein.  Durch die Übergabe des Pfads als Argument an das WSDL\-Tool wird ein clientseitiger Proxy in demselben Verzeichnis und Namespace wie Ihre Anwendung sowie in der angegebenen Sprache generiert.  Wenn Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] verwenden, fügen Sie die Datei zu Ihrem Projekt hinzu.  
  
5.  Wählen Sie im clientseitigen Proxy einen Typ für die Bindung aus.  
  
     Dies ist normalerweise ein Typ, der von einer vom Webdienst angebotenen Methode zurückgegeben wird.  Die Felder des ausgewählten Typs müssen zu Bindungszwecken als öffentliche Eigenschaften verfügbar gemacht werden.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  Legen Sie für die <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft von <xref:System.Windows.Forms.BindingSource> den gewünschten Typ fest, der im clientseitigen Proxy des Webdiensts enthalten ist.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### So binden Sie Steuerelemente an die Bindungsquelle, die an einen Webdienst gebunden ist  
  
-   Binden Sie Steuerelemente an <xref:System.Windows.Forms.BindingSource>, wobei Sie die öffentliche Eigenschaft des Webdiensttyps übergeben, den Sie als Parameter verwenden möchten.  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht das Binden einer <xref:System.Windows.Forms.BindingSource>\-Komponente an einen Webdienst und das anschließende Binden eines Textfelds an die <xref:System.Windows.Forms.BindingSource>\-Komponente.  Wenn Sie auf die Schaltfläche klicken, wird eine Webdienstmethode aufgerufen und die Ergebnisse werden in `textbox1` angezeigt.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## Kompilieren des Codes  
 Dies ist ein vollständiges Beispiel, das eine `Main`\-Methode und eine verkürzte Version des clientseitigen Proxycodes enthält.  
  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing", "System.Web.Services", "System.Windows.Forms" und "System.Xml".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Gewusst wie: Binden eines Windows Forms\-Steuerelements an einen Typ](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
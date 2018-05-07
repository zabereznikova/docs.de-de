---
title: 'Vorgehensweise: Exportieren von benutzerdefinierter WSDL'
ms.date: 03/30/2017
ms.assetid: 5c1e4b58-b76b-472b-9635-2f80d42a0734
ms.openlocfilehash: 82f343d5e2637ff1330570a01b376e83567db4f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-export-custom-wsdl"></a>Vorgehensweise: Exportieren von benutzerdefinierter WSDL
Dieses Thema erklärt, wie benutzerdefinierte WSDL-Informationen exportiert werden. Hierfür muss ein neues Codeattribut namens `WsdlDocumentationAttribute` definiert werden, dass der von diesem Dienst generierten WSDL benutzerdefinierte Informationen hinzufügen wird.  
  
### <a name="to-export-custom-wsdl-information"></a>Benutzerdefinierte WSDL-Informationen exportieren  
  
1.  Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlExportExtension>-Schnittstelle. Diese Schnittstelle kann auf einer Klasse implementiert werden, die eine der folgenden Schnittstellen implementiert: <xref:System.ServiceModel.Description.IOperationBehavior>, <xref:System.ServiceModel.Description.IContractBehavior> oder <xref:System.ServiceModel.Description.IEndpointBehavior>. Sie kann auch auf einer Klasse, die von <xref:System.ServiceModel.Channels.BindingElement> abgeleitet wird, implementiert werden. In diesem Beispiel wird <xref:System.ServiceModel.Description.IWsdlExportExtension>  auf einer Attributklasse implementiert, die <xref:System.ServiceModel.Description.IContractBehavior> implementiert.  
  
2.  <xref:System.ServiceModel.Description.IWsdlExportExtension> definiert zwei Methoden <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> und <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>. Mithilfe dieser Methoden können Sie Informationen in <xref:System.ServiceModel.Description.WsdlContractConversionContext> ändern oder zusätzliche Informationen hinzufügen (oder sowohl ändern als auch hinzufügen). Dieses Beispiel ruft in der Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> eine Sammlung von <xref:System.ServiceModel.Description.OperationDescription>-Objekten auf und iteriert dann durch die Sammlung auf der Suche nach einem `WsdlDocumentationAttribute`. Wenn eines gefunden wird, wird der mit dem Attribut verbundene Text extrahiert, es wird ein Zusammenfassungselement generiert, und das Zusammenfassungselement wird dem `DocumentationElement` des Vorgangs hinzugefügt.  
  
    ```  
            public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
    {  
                Console.WriteLine("Inside ExportContract");  
    if (context.Contract != null)  
    {  
                    // Set the document element; if this is not done first, there is no XmlElement in the   
                    // DocumentElement property.  
                    context.WsdlPortType.Documentation = string.Empty;   
                    // Contract comments.  
                    XmlDocument owner = context.WsdlPortType.DocumentationElement.OwnerDocument;  
                    XmlElement summaryElement = Formatter.CreateSummaryElement(owner, this.Text);   
                    context.WsdlPortType.DocumentationElement.AppendChild(summaryElement);  
  
                    foreach (OperationDescription op in context.Contract.Operations)  
                    {  
                        Operation operation = context.GetOperation(op);  
                        object[] opAttrs = op.SyncMethod.GetCustomAttributes(typeof(WsdlDocumentationAttribute), false);  
                        if (opAttrs.Length == 1)  
                        {  
                            string opComment = ((WsdlDocumentationAttribute)opAttrs[0]).Text;  
  
                            // This.Text returns the string for the operation-level attributes.  
                            // Set the doc element; if this is not done first, there is no XmlElement in the   
                            // DocumentElement property.  
                            operation.Documentation = String.Empty;  
  
                            XmlDocument opOwner = operation.DocumentationElement.OwnerDocument;  
                            XmlElement newSummaryElement = Formatter.CreateSummaryElement(opOwner, opComment);  
                            operation.DocumentationElement.AppendChild(newSummaryElement);  
                        }  
                    }  
                }  
    ```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die komplette Implementierung der Klasse `WsdlDocumentationAttribute` veranschaulicht.  
  
```  
public class WsdlDocumentationAttribute : Attribute, IContractBehavior, IWsdlExportExtension  
{  
string text;  
       XmlElement customWsdlDocElement = null;  
public WsdlDocumentationAttribute(string text)  
{ this.text = text;}  
  
       public WsdlDocumentationAttribute(XmlElement wsdlDocElement)  
        { this.customWsdlDocElement = wsdlDocElement; }  
  
        public XmlElement WsdlDocElement  
        {  
            get { return this.customWsdlDocElement; }  
            set { this.customWsdlDocElement = value; }  
        }  
       public string Text  
{  
get { return this.text; }  
set { this.text = value; }  
}  
  
     public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
          Console.WriteLine("Inside ExportContract");  
if (context.Contract != null)  
{  
                // Set the document element; if this is not done first, there is no XmlElement in the   
                // DocumentElement property.  
                context.WsdlPortType.Documentation = string.Empty;   
                // Contract comments.  
                XmlDocument owner = context.WsdlPortType.DocumentationElement.OwnerDocument;  
                XmlElement summaryElement = Formatter.CreateSummaryElement(owner, this.Text);   
                context.WsdlPortType.DocumentationElement.AppendChild(summaryElement);  
  
                foreach (OperationDescription op in context.Contract.Operations)  
                {  
                    Operation operation = context.GetOperation(op);  
                    object[] opAttrs = op.SyncMethod.GetCustomAttributes(typeof(WsdlDocumentationAttribute), false);  
                    if (opAttrs.Length == 1)  
                    {  
                        string opComment = ((WsdlDocumentationAttribute)opAttrs[0]).Text;  
  
                        // This.Text returns the string for the operation-level attributes.  
                        // Set the document element; if this is not done first, there is no XmlElement in the   
                        // DocumentElement property.  
                        operation.Documentation = String.Empty;  
  
                        XmlDocument opOwner = operation.DocumentationElement.OwnerDocument;  
                        XmlElement newSummaryElement = Formatter.CreateSummaryElement(opOwner, opComment);  
                        operation.DocumentationElement.AppendChild(newSummaryElement);  
                    }  
                }  
            }  
        }  
  
public void ExportEndpoint(WsdlExporter exporter, WsdlEndpointConversionContext context)   
        {  
            Console.WriteLine("ExportEndpoint called.");  
        }  
  
        public void AddBindingParameters(ContractDescription description, ServiceEndpoint endpoint, BindingParameterCollection parameters)  
        { return; }  
  
        public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, ClientRuntime client)  
        { return; }  
  
        public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
        { return; }  
  
        public void Validate(ContractDescription description, ServiceEndpoint endpoint) { return; }  
    }  
  
  public class Formatter  
  {  
  
#region Utility Functions  
  
    public static XmlElement CreateSummaryElement(XmlDocument owningDoc, string text)  
    {  
      XmlElement summaryElement = owningDoc.CreateElement("summary");  
      summaryElement.InnerText = text;  
      return summaryElement;  
    }  
  
public static CodeCommentStatementCollection FormatComments(string text)  
{  
      /*  
       * Note that in Visual C# the XML comment format absorbs a   
       * documentation element with a line break in the middle. This sample  
       * could take an XmlElement and create code comments in which   
       * the element never had a line break in it.  
      */  
  
      CodeCommentStatementCollection collection = new CodeCommentStatementCollection();  
collection.Add(new CodeCommentStatement("From WsdlDocumentation:", true));  
collection.Add(new CodeCommentStatement(String.Empty, true));  
  
foreach (string line in WordWrap(text, 80))  
{  
collection.Add(new CodeCommentStatement(line, true));  
}  
  
collection.Add(new CodeCommentStatement(String.Empty, true));  
return collection;  
}  
  
public static Collection<string> WordWrap(string text, int columnWidth)  
{  
Collection<string> lines = new Collection<string>();  
System.Text.StringBuilder builder = new System.Text.StringBuilder();  
  
string[] words = text.Split(' ');  
foreach (string word in words)  
{  
if ((builder.Length > 0) && ((builder.Length + word.Length + 1) > columnWidth))  
{  
lines.Add(builder.ToString());  
builder = new System.Text.StringBuilder();  
}  
builder.Append(word);  
builder.Append(' ');  
}  
lines.Add(builder.ToString());  
  
return lines;  
}  
  
#endregion    
  
    public static XmlElement CreateReturnsElement(XmlDocument owner, string p)  
    {  
      XmlElement returnsElement = owner.CreateElement("returns");  
      returnsElement.InnerText = p;  
      return returnsElement;  
    }  
  }  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md)

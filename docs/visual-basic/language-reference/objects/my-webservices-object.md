---
title: My.WebServices-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 9519638c7609b9b1d0f5e07397c46975e2696c94
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604691"
---
# <a name="mywebservices-object"></a>My.WebServices-Objekt
Stellt Eigenschaften zum Erstellen und den Zugriff auf eine einzelne Instanz jeder XML-Webdienst auf, die vom aktuellen Projekt verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.WebServices`-Objekt bietet eine Instanz jedes Webdienstes, auf den vom aktuellen Projekt verwiesen wird. Jede Instanz wird bei Bedarf instanziiert. Sie können über die Eigenschaften des `My.WebServices`-Objekts auf diese Webdienste zugreifen. Der Name der Eigenschaft stimmt mit dem des Webdienstes überein, auf den die Eigenschaft zugreift. Jede Klasse, die von <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> erbt, ist ein Webdienst. Informationen zum Hinzufügen von Webdiensten zu einem Projekt finden Sie unter [zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Die `My.WebServices` Objekt macht nur der Web-Dienste, die mit dem aktuellen Projekt verknüpft sind. Es bietet keine auf Webdienste, die in der referenzierten DLLs deklariert. Zum Zugriff auf einen Webdienst, der eine DLL-Datei bereitstellt, müssen Sie den qualifizierten Namen des Webdiensts, verwenden, in der Form *DLL-Namen*. *WebServiceName*. Weitere Informationen finden Sie unter [zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Das Objekt und seine Eigenschaften sind nicht für Webanwendungen verfügbar.  
  
## <a name="properties"></a>Eigenschaften  
 Jede Eigenschaft der `My.WebServices` -Objekt bietet Zugriff auf eine Instanz eines Webdiensts, die vom aktuellen Projekt verwiesen wird. Der Name der Eigenschaft ist identisch mit den Namen des Webdiensts, der die Eigenschaft zugreift, und der Eigenschaftstyp ist identisch mit dem Webdienst-Typ.  
  
> [!NOTE]
>  Ist ein Konflikt von geschachteltem Klassennamen, der Eigenschaftsname für den Zugriff auf einen Webdienst ist *RootNamespace*_*Namespace*\_*ServiceName*. Betrachten Sie beispielsweise zwei Webdienste mit dem Namen `Service1`. Wenn einer dieser Dienste im Stammnamespace ist `WindowsApplication1` und im Namespace `Namespace1`, würden Sie diesen Dienst zugreifen, mithilfe von `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Beim ersten Zugriff auf eines der `My.WebServices` Objekteigenschaften, er erstellt eine neue Instanz des Webdiensts und speichert sie. Nachfolgende Zugriffe dieser Eigenschaft zurückgeben dieser Instanz des Webdiensts.  
  
 Sie können durch Zuweisen eines Webdiensts dispose `Nothing` für die Eigenschaft für diesen Webdienst. Der Eigenschaftensetter weist `Nothing` mit dem gespeicherten Wert. Wenn Sie einen beliebigen Wert außer zuweisen `Nothing` der Eigenschaft Setter-Methode löst eine <xref:System.ArgumentException> Ausnahme.  
  
 Sie können testen, ob eine Eigenschaft der `My.WebServices` Objekt speichert eine Instanz des Webdiensts mithilfe der `Is` oder `IsNot` Operator. Sie können diese Operatoren verwenden, zum Überprüfen, ob der Wert der Eigenschaft ist `Nothing`.  
  
> [!NOTE]
>  In der Regel die `Is` oder `IsNot` Operator muss den Wert der Eigenschaft zum Ausführen des Vergleichs zu lesen. Jedoch, wenn die Eigenschaft aktuell speichert `Nothing`, die Eigenschaft erstellt eine neue Instanz des Webdiensts und gibt dann diese Instanz zurück. Visual Basic-Compiler behandelt jedoch die Eigenschaften der `My.WebServices` speziell Objekt, und ermöglicht die `Is` oder `IsNot` Operator, um den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel ruft die `FahrenheitToCelsius` Methode der `TemperatureConverter` XML-Webdienst, und gibt das Ergebnis zurück.  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 Für dieses Beispiel funktioniert, muss das Projekt verweisen, einen Webdienst mit dem Namen `Converter`, und dem Webdienst verfügbar machen die `ConvertTemperature` Methode. Weitere Informationen finden Sie unter [zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Dieser Code funktioniert nicht in einem Webprojekt für die Anwendung.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="availability-by-project-type"></a>Verfügbarkeit nach Projekttyp  
  
|Projekttyp:|Verfügbar|  
|---|---|  
|Windows-Anwendung|**Ja**|  
|Klassenbibliothek|**Ja**|  
|Konsolenanwendung|**Ja**|  
|Windows-Steuerelementbibliothek|**Ja**|  
|Websteuerelementbibliothek|**Ja**|  
|Windows-Dienst|**Ja**|  
|Website|Nein|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [Zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)

---
title: My.WebServices-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 290d025985663bc45fe605a2e9904fc90fb2bc63
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350339"
---
# <a name="mywebservices-object"></a>My.WebServices-Objekt
Stellt Eigenschaften zum Erstellen von und Zugreifen auf eine einzelne Instanz eines XML-Webdiensts bereit, auf den vom aktuellen Projekt verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.WebServices`-Objekt bietet eine Instanz jedes Webdienstes, auf den vom aktuellen Projekt verwiesen wird. Jede Instanz wird bei Bedarf instanziiert. Sie können über die Eigenschaften des `My.WebServices`-Objekts auf diese Webdienste zugreifen. Der Name der Eigenschaft stimmt mit dem des Webdienstes überein, auf den die Eigenschaft zugreift. Jede Klasse, die von <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> erbt, ist ein Webdienst. Weitere Informationen zum Hinzufügen von Webdiensten zu einem Projekt finden Sie unter [zugreifen auf Anwendungsweb Dienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Das `My.WebServices`-Objekt macht nur die Webdienste verfügbar, die mit dem aktuellen Projekt verknüpft sind. Er bietet keinen Zugriff auf die in referenzierten DLLs deklarierten Webdienste. Um auf einen Webdienst zuzugreifen, den eine DLL bereitstellt, müssen Sie den qualifizierten Namen des Webdiensts im Format " *dllName*" verwenden. *WebServiceName*. Weitere Informationen finden Sie unter [zugreifen auf Anwendungsweb Dienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Das-Objekt und seine Eigenschaften sind für Webanwendungen nicht verfügbar.  
  
## <a name="properties"></a>Eigenschaften  
 Jede Eigenschaft des `My.WebServices` Objekts ermöglicht den Zugriff auf eine Instanz eines Webdiensts, auf den vom aktuellen Projekt verwiesen wird. Der Name der Eigenschaft ist identisch mit dem Namen des Webdiensts, auf den die Eigenschaft zugreift, und der Eigenschaftentyp entspricht dem Typ des Webdiensts.  
  
> [!NOTE]
> Wenn ein namens Konflikt vorliegt, ist der Eigenschaftsname für den Zugriff auf einen Webdienst *RootNamespace*_*Namespace*\_*ServiceName*. Sehen Sie sich beispielsweise zwei Webdienste mit dem Namen `Service1`an. Wenn sich einer dieser Dienste im Stamm Namespace befindet `WindowsApplication1` und im Namespace `Namespace1`, können Sie mit `My.WebServices.WindowsApplication1_Namespace1_Service1`auf diesen Dienst zugreifen.  
  
 Wenn Sie zum ersten Mal auf eine der Eigenschaften des `My.WebServices` Objekts zugreifen, wird eine neue Instanz des Webdiensts erstellt und gespeichert. Bei nachfolgenden Zugriffen dieser Eigenschaft wird diese Instanz des Webdiensts zurückgegeben.  
  
 Sie können einen Webdienst verwerfen, indem Sie `Nothing` der-Eigenschaft für diesen Webdienst zuweisen. Der Eigenschaften Setter weist `Nothing` dem gespeicherten Wert zu. Wenn Sie der-Eigenschaft einen anderen Wert als `Nothing` zuweisen, löst der Setter eine <xref:System.ArgumentException>-Ausnahme aus.  
  
 Sie können überprüfen, ob eine Eigenschaft des `My.WebServices` Objekts eine Instanz des Webdiensts speichert, indem Sie den `Is`-oder `IsNot`-Operator verwenden. Sie können diese Operatoren verwenden, um zu überprüfen, ob der Wert der Eigenschaft `Nothing`ist.  
  
> [!NOTE]
> In der Regel muss der `Is` oder `IsNot` Operator den Wert der-Eigenschaft lesen, um den Vergleich durchzuführen. Wenn die Eigenschaft derzeit jedoch `Nothing`speichert, erstellt die-Eigenschaft eine neue Instanz des Webdiensts und gibt diese Instanz zurück. Der Visual Basic Compiler behandelt jedoch die Eigenschaften des `My.WebServices` Objekts speziell und ermöglicht dem `Is` oder `IsNot` Operator, den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die `FahrenheitToCelsius`-Methode des `TemperatureConverter` XML-Webdiensts aufgerufen und das Ergebnis zurückgegeben.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Damit dieses Beispiel funktioniert, muss das Projekt auf einen Webdienst namens `Converter`verweisen, und dieser Webdienst muss die `ConvertTemperature`-Methode verfügbar machen. Weitere Informationen finden Sie unter [zugreifen auf Anwendungsweb Dienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Dieser Code funktioniert nicht in einem Webanwendungs Projekt.  
  
## <a name="requirements"></a>Voraussetzungen  
  
### <a name="availability-by-project-type"></a>Verfügbarkeit nach Projekttyp  
  
|Projekttyp:|Verfügbar|  
|---|---|  
|Windows-Anwendung|**Ja**|  
|Klassenbibliothek|**Ja**|  
|Konsolenanwendung|**Ja**|  
|Windows-Steuerelement Bibliothek|**Ja**|  
|Websteuer Element Bibliothek|**Ja**|  
|Windows-Dienst|**Ja**|  
|Website|Nein|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)

---
title: My.WebServices-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: a60f32c4f581e42f240fca55ce496776c5511ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050284"
---
# <a name="mywebservices-object"></a>My.WebServices-Objekt
Stellt Eigenschaften bereit, für das Erstellen und den Zugriff auf eine einzelne Instanz jeder XML-Webdienst, der vom aktuellen Projekt verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Das `My.WebServices`-Objekt bietet eine Instanz jedes Webdienstes, auf den vom aktuellen Projekt verwiesen wird. Jede Instanz wird bei Bedarf instanziiert. Sie können über die Eigenschaften des `My.WebServices`-Objekts auf diese Webdienste zugreifen. Der Name der Eigenschaft stimmt mit dem des Webdienstes überein, auf den die Eigenschaft zugreift. Jede Klasse, die von <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> erbt, ist ein Webdienst. Informationen zum Hinzufügen von Webdiensten zu einem Projekt finden Sie unter [zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Die `My.WebServices` Objekt verfügbar macht, nur die Webdienste, die mit dem aktuellen Projekt verknüpft ist. Er bietet Zugriff auf Webdienste, die in referenzierten DLLs deklariert. Zum Zugriff auf einen Webdienst, der eine DLL-Datei bereitstellt, müssen Sie den qualifizierten Namen des Webdiensts, verwenden, in der Form *DllName*. *WebServiceName*. Weitere Informationen finden Sie unter [zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Das Objekt und seine Eigenschaften sind nicht für Webanwendungen verfügbar.  
  
## <a name="properties"></a>Eigenschaften  
 Jede Eigenschaft der `My.WebServices` -Objekt bietet Zugriff auf eine Instanz eines Webdiensts, der vom aktuellen Projekt verwiesen wird. Der Name der Eigenschaft ist identisch mit den Namen des Webdiensts, der die Eigenschaft zugreift, und der Eigenschaftentyp ist der gleiche wie der Webdienst-Typ.  
  
> [!NOTE]
>  Bei ein Namenskonflikt wird der Eigenschaftsname für den Zugriff auf einen Webdienst ist *RootNamespace*_*Namespace*\_*ServiceName*. Betrachten Sie beispielsweise zwei Webdienste, die mit dem Namen `Service1`. Wenn einer dieser Dienste im Stammnamespace ist `WindowsApplication1` und im Namespace `Namespace1`, greifen Sie mithilfe dieses Diensts `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 Beim ersten Zugriff auf eines der `My.WebServices` Objekteigenschaften, er erstellt eine neue Instanz des Webdiensts und speichert sie. Diese Instanz des Webdiensts zurück nachfolgenden Zugriff dieser Eigenschaft  
  
 Sie können durch Zuweisen eines Webdiensts dispose `Nothing` der Eigenschaft für diesen Webdienst. Weist der Eigenschaftensetter `Nothing` gespeicherten Wert. Wenn Sie einen beliebigen Wert außer zuweisen `Nothing` löst der Setter der Eigenschaft ein <xref:System.ArgumentException> Ausnahme.  
  
 Sie können testen, ob eine Eigenschaft der `My.WebServices` Objekt wird eine Instanz des Webdiensts mithilfe der `Is` oder `IsNot` Operator. Sie können diese Operatoren verwenden, um zu überprüfen, ob der Wert der Eigenschaft ist `Nothing`.  
  
> [!NOTE]
>  In der Regel die `Is` oder `IsNot` Operator muss den Wert der Eigenschaft zum Ausführen des Vergleichs zu lesen. Aber wenn die Eigenschaft derzeit speichert `Nothing`, die Eigenschaft erstellt eine neue Instanz des Webdiensts und gibt dann diese Instanz zurück. Visual Basic-Compiler behandelt jedoch die Eigenschaften der `My.WebServices` speziell Objekt aus, und ermöglicht die `Is` oder `IsNot` Operator, um den Status der Eigenschaft zu überprüfen, ohne Änderung ihres Werts.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel ruft die `FahrenheitToCelsius` Methode der `TemperatureConverter` XML-Webdienst und das Ergebnis zurückgibt.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Für dieses Beispiel funktioniert, muss das Projekt verweisen, einen Webdienst, der mit dem Namen `Converter`, und muss diesen Webdienst verfügbar zu machen die `ConvertTemperature` Methode. Weitere Informationen finden Sie unter [zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Dieser Code funktioniert nicht in ein Webanwendungsprojekt.  
  
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

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Zugreifen auf Anwendungswebdienste](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)

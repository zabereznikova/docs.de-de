---
title: LINQ to XML-Ereignisse
ms.date: 07/20/2015
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
ms.openlocfilehash: 06191fb94f808d9a3ece8de000dec1c5de769dde
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351928"
---
# <a name="linq-to-xml-events-visual-basic"></a>Ereignisse LINQ to XML (Visual Basic)
Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignissen können Sie sich benachrichtigen lassen, wenn eine XML-Struktur geändert wird.  
  
 Ereignisse können allen Instanzen eines <xref:System.Xml.Linq.XObject> hinzugefügt werden. Der Ereignishandler empfängt dann Ereignisse für Änderungen an diesem <xref:System.Xml.Linq.XObject> und dessen Nachfolgern. So können Sie z. B. dem Stamm der Struktur einen Ereignishandler hinzufügen und alle Änderungen an der Struktur von diesem Ereignishandler behandeln lassen.  
  
 Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignisse finden Sie unter <xref:System.Xml.Linq.XObject.Changing> und <xref:System.Xml.Linq.XObject.Changed>.  
  
## <a name="types-and-events"></a>Typen und Ereignisse  
 Beim Arbeiten mit Ereignissen stehen Ihnen die folgenden Typen zur Verfügung:  
  
|Typ|Beschreibung|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|Gibt den Ereignistyp an, wenn ein Ereignis für ein <xref:System.Xml.Linq.XObject> ausgelöst wird.|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|Stellt Daten für das <xref:System.Xml.Linq.XObject.Changing>-Ereignis und das <xref:System.Xml.Linq.XObject.Changed>-Ereignis bereit.|  
  
 Die folgenden Ereignisse werden ausgelöst, wenn Sie eine XML-Struktur ändern:  
  
|Ereignis|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|Tritt ein, unmittelbar bevor sich dieses <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger ändert.|  
|<xref:System.Xml.Linq.XObject.Changed>|Tritt ein, wenn sich ein <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger geändert hat.|  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Ereignisse erweisen sich als nützlich, wenn aggregierte Informationen in einer XML-Struktur bereitgestellt werden sollen. So können Sie auf diese Weise z. B. einen Rechnungsgesamtbetrag bereitstellen, der sich aus der Summe der Einzelpositionen der Rechnung ergibt. Dieses Beispiel verwendet Ereignisse, um den Gesamtbetrag aller untergeordneten Elemente des komplexen Elements `Items` bereitzustellen:  
  
### <a name="code"></a>Code  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Comments  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```console  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Erweiterte LINQ to XML Programmierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

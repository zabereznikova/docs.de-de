---
title: Event-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Event
- vb.Custom
dev_langs:
- VB
helpviewer_keywords:
- Event statement
- declaring events, syntax
- Public keyword, Event statements
- Custom keyword
- declarations, events
- event keyword [Visual Basic]
- WithEvents keyword, Event statements
- events [Visual Basic], declaring
- ByVal keyword, Event statements
- events [Visual Basic], custom
- ByRef keyword, Event statements
- declaring user-defined events
ms.assetid: 306ff8ed-74dd-4b6a-bd2f-e91b17474042
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b0ea8074f996622df3cd88a7e87fc1156b63dcaf
ms.lasthandoff: 03/13/2017

---
# <a name="event-statement"></a>Event-Anweisung
Deklariert ein benutzerdefiniertes Ereignis.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname[(parameterlist)] _  
[ Implements implementslist ]  
' -or-  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname As delegatename _  
[ Implements implementslist ]  
' -or-  
 [ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Custom Event eventname As delegatename _  
[ Implements implementslist ]  
   [ <attrlist> ] AddHandler(ByVal value As delegatename)  
      [ statements ]  
   End AddHandler  
   [ <attrlist> ] RemoveHandler(ByVal value As delegatename)  
      [ statements ]  
   End RemoveHandler  
   [ <attrlist> ] RaiseEvent(delegatesignature)  
      [ statements ]  
   End RaiseEvent  
End Event  
```  
  
## <a name="parts"></a>Teile  
  
|Segment|Beschreibung|  
|---|---|  
|`attrlist`|Optional. Liste der Attribute, die für dieses Ereignis gelten. Mehrere Attribute werden durch Kommas getrennt. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").|  
|`accessmodifier`|Optional. Gibt an, welcher Code auf dieses Ereignis zugreifen kann. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)– Code, der das Element zugreifen kann, die es deklariert, kann darauf zugreifen.<br />-   [Geschützte](../../../visual-basic/language-reference/modifiers/protected.md)– nur Code innerhalb seiner Klasse oder einer abgeleiteten Klasse darauf zugreifen kann.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)– nur Code in der gleichen Assembly kann darauf zugreifen.<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)– nur Code innerhalb des Elements, das es deklariert, kann darauf zugreifen.<br /><br /> Sie können `Protected Friend` angeben, um den Zugriff auf den Code in der Klasse des Ereignisses, einer abgeleiteten Klasse oder derselben Assembly zu ermöglichen.|  
|`Shared`|Optional. Gibt an, dass dieses Ereignis nicht mit einer bestimmten Instanz einer Klasse oder Struktur verknüpft ist.|  
|`Shadows`|Optional. Gibt an, dass dieses Ereignis ein identisch benanntes Programmierelement oder einen Satz überladener Elemente in einen Basisklasse erneut deklariert und ausblendet. Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen.<br /><br /> Ein schattiertes Element steht in der abgeleiteten Klasse, die es spiegelt, nicht zur Verfügung, und zwar mit Ausnahme von dem Punkt, wo nicht auf das Shadowing-Element zugriffen werden kann. Wenn beispielsweise ein `Private`-Element ein Basisklassenelement spiegelt, greift der Code, der nicht über die Berechtigung für den Zugriff auf das `Private`-Element verfügt, anstelle auf das Basisklassenelement zu.|  
|`eventname`|Erforderlich. Der Name des Ereignisses; folgt standardmäßigen Variablennamenskonventionen.|  
|`parameterlist`|Optional. Liste der lokalen Variablen, die die Parameter dieses Ereignisses darstellen. Setzen Sie die [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md) in Klammern.|  
|`Implements`|Optional. Gibt an, dass dieses Ereignis ein Ereignis einer Schnittstelle implementiert.|  
|`implementslist`|Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Sub`-Prozeduren. Mehrere Prozeduren werden durch Kommas getrennt:<br /><br /> *Implementedprocedure* [, *Implementedprocedure* ...]<br /><br /> Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:<br /><br /> `interface`.`definedname`<br /><br /> -   `interface`-Erforderlich. Name einer Schnittstelle, die von der in dieser Prozedur enthaltenen Klasse oder Struktur implementiert wird.<br />-   `Definedname`-Erforderlich. Name, wodurch die Prozedur in `interface` definiert ist. Hierbei muss es sich nicht um demselben Namen wie `name` (den Namen, den dieser Prozedur verwendet, um die definierte Prozedur zu implementieren) handeln.|  
|`Custom`|Erforderlich. Als `Custom` deklarierte Ereignisse müssen benutzerdefinierte `AddHandler`-, `RemoveHandler`- und `RaiseEvent`-Accessoren definieren.|  
|`delegatename`|Optional. Der Name eines Delegaten, der die Signatur des Ereignishandlers angibt.|  
|`AddHandler`|Erforderlich. Deklariert einen `AddHandler`-Accessor, der die auszuführenden Anweisungen angibt, wenn ein Ereignishandler hinzugefügt wird, und zwar entweder explizit mithilfe der `AddHandler`-Anweisung oder implizit mithilfe der `Handles`-Klausel.|  
|`End AddHandler`|Erforderlich. Beendet den `AddHandler`-Block.|  
|`value`|Erforderlich. Parametername.|  
|`RemoveHandler`|Erforderlich. Deklariert einen `RemoveHandler`-Accessor, der die auszuführenden Anweisungen angibt, wenn ein Ereignishandler mithilfe der `RemoveHandler`-Anweisung entfernt wird.|  
|`End RemoveHandler`|Erforderlich. Beendet den `RemoveHandler`-Block.|  
|`RaiseEvent`|Erforderlich. Deklariert einen `RaiseEvent`-Accessor, der die auszuführenden Anweisungen angibt, wenn ein Ereignis mithilfe der `RaiseEvent`-Anweisung ausgelöst wird. Für gewöhnlich wird dadurch eine Liste der Delegaten aufgerufen, die durch die `AddHandler`- und `RemoveHandler`-Accessoren verwaltet werden.|  
|`End RaiseEvent`|Erforderlich. Beendet den `RaiseEvent`-Block.|  
|`delegatesignature`|Erforderlich. Liste der Parameter, die mit dem Parametern übereinstimmen, die durch das `delegatename`-Delegat erforderlich sind. Setzen Sie die [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md) in Klammern.|  
|`statements`|Optional. Anweisungen, die die Textteile der Methoden `AddHandler`, `RemoveHandler` und `RaiseEvent` enthalten.|  
|`End Event`|Erforderlich. Beendet den `Event`-Block.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie nach erfolgter Deklarierung des Ereignisses die Anweisung `RaiseEvent` zum Auslösen des Ereignisses. Ein typisches Ereignis könnte analog zur Darstellung in den folgenden Fragmenten deklariert und ausgelöst werden.  
  
 [!code-vb[VbVbalrEvents&#13;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_1.vb)]  
  
> [!NOTE]
>  Sie können Ereignisargumente deklarieren, wie Sie dies bei Argumenten von Prozeduren vornehmen, und zwar mit den folgenden Ausnahmen: Ereignisse können nicht über benannte Argumente, `ParamArray`- oder `Optional`-Argumente verfügen. Ereignisse haben keine Rückgabewerte.  
  
 Zum Verarbeiten eines Ereignisses müssen Sie es mithilfe der Anweisung `Handles` oder `AddHandler` mit einer Ereignishandler-Unterroutine verknüpfen. Die Signaturen der Unterroutine und des Ereignisses müssen übereinstimmen. Zum Verarbeiten eines freigegebenen Ereignisses müssen Sie die Anweisung `AddHandler` verwenden.  
  
 Sie können `Event` nur auf Modulebene verwenden. Dies bedeutet, dass die *Deklarationskontext* für ein Ereignis eine Klasse, Struktur, Modul oder Schnittstelle sein muss und darf keine Quelldatei, Namespace, Prozedur oder Block. Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 In den meisten Fällen können Sie zum Deklarieren von Ereignissen die erste Syntax im Syntaxabschnitt dieses Themas verwenden. In einigen Szenarien ist es jedoch erforderlich, dass Sie mehr Kontrolle über das detaillierte Verhalten des Ereignisses verfügen. Die letzte Syntax im Syntaxabschnitt dieses Themas, die das Schlüsselwort `Custom` verwendet, enthält diese Steuerung, indem Ihnen ermöglicht wird, benutzerdefinierte Ereignisse zu definieren. In einem benutzerdefinierten Ereignis geben Sie genau an, was geschieht, wenn ein Ereignishandler mithilfe von Code zum Ereignis hinzugefügt oder daraus entfernt wird oder wenn der Code das Ereignis auslöst. Beispiele finden Sie unter [wie: Deklarieren benutzerdefinierte Ereignisse zu sparen Speicher](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md) und [Gewusst wie: Deklarieren Sie benutzerdefinierte Ereignisse zu vermeiden blockieren](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet. Der Code veranschaulicht mehrere der ereignisbezogene Methoden, Eigenschaften und Anweisungen. Dies schließt die `RaiseEvent`-Anweisung mit ein.  
  
 Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler. Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert. Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.  
  
 Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet. Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
 Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an. Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.  
  
 Um dieses Beispiel zu verwenden, öffnen Sie ein neues Windows Forms-Projekt. Fügen Sie dem Hauptformular mit dem Namen `Form1` anschließend eine Schaltfläche mit dem Namen `Button1` und ein Textfeld mit dem Namen `TextBox1` hinzu. Klicken Sie dann mit der rechten Maustaste in des Formulars, und klicken Sie auf **Anzeigecode** Code-Editor zu öffnen.  
  
 Fügen Sie eine `WithEvents`-Variable zum Deklarationsabschnitt der `Form1`-Klasse hinzu:  
  
 [!code-vb[VbVbalrEvents&14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_2.vb)]  
  
 Fügen Sie den folgenden Code zum Code für `Form1` hinzu. Ersetzen Sie ggf. vorhandene doppelte Prozeduren, beispielsweise `Form_Load` oder `Button_Click`.  
  
 [!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_3.vb)]  
  
 Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche **Start**. Im ersten Textfeld werden die Sekunden heruntergezählt. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
> [!NOTE]
>  Die `My.Application.DoEvents`-Methode verarbeitet Ereignisse nicht in der gleichen Weise wie das Formular. Damit das Formular die Ereignisse direkt verarbeiten kann, können Sie Multithreading verwenden. Weitere Informationen finden Sie unter [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
## <a name="see-also"></a>Siehe auch  
 [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)   
 [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)   
 [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um die Blockierung zu vermeiden](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)   
 [Freigegebene](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)

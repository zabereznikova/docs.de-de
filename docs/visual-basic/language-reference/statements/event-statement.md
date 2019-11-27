---
title: Event-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Event
- vb.Custom
helpviewer_keywords:
- Event statement [Visual Basic]
- declaring events [Visual Basic], syntax
- Public keyword [Visual Basic], Event statements
- Custom keyword [Visual Basic]
- declarations [Visual Basic], events
- event keyword [Visual Basic]
- WithEvents keyword [Visual Basic], Event statements
- events [Visual Basic], declaring
- ByVal keyword [Visual Basic], Event statements
- events [Visual Basic], custom
- ByRef keyword [Visual Basic], Event statements
- declaring user-defined events
ms.assetid: 306ff8ed-74dd-4b6a-bd2f-e91b17474042
ms.openlocfilehash: dd42e3364d96a8a9b3800b3d1f5e94b2fa25bad4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351228"
---
# <a name="event-statement"></a>Event-Anweisung
Deklariert ein benutzerdefiniertes Ereignis.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
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
  
## <a name="parts"></a>-Komponenten  
  
|-Komponente|Beschreibung|  
|---|---|  
|`attrlist`|Optional. Liste der Attribute, die für dieses Ereignis gelten. Mehrere Attribute werden durch Kommas getrennt. Sie müssen die [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`" und "`>`") einschließen.|  
|`accessmodifier`|Optional. Gibt an, welcher Code auf dieses Ereignis zugreifen kann. Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)– jeder Code, der auf das Element zugreifen kann, das es deklariert, kann darauf zugreifen.<br />-   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)– nur Code in der Klasse oder einer abgeleiteten Klasse kann darauf zugreifen.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)– nur Code in derselben Assembly kann darauf zugreifen.<br />-   [private](../../../visual-basic/language-reference/modifiers/private.md)– nur Code in dem Element, das Sie deklariert, kann darauf zugreifen.<br /> -   [geschützter](../../language-reference/modifiers/protected-friend.md)nur-Friend-Code in der-Klasse des Ereignisses, eine abgeleitete Klasse oder dieselbe Assembly kann darauf zugreifen. <br />- [privaten, geschützten](../../language-reference/modifiers/private-protected.md)Code in der-Klasse des Ereignisses oder eine abgeleitete Klasse in derselben Assembly kann darauf zugreifen.|  
|`Shared`|Optional. Gibt an, dass dieses Ereignis nicht mit einer bestimmten Instanz einer Klasse oder Struktur verknüpft ist.|  
|`Shadows`|Optional. Gibt an, dass dieses Ereignis ein identisch benanntes Programmierelement oder einen Satz überladener Elemente in einen Basisklasse erneut deklariert und ausblendet. Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen.<br /><br /> Ein schattiertes Element steht in der abgeleiteten Klasse, die es spiegelt, nicht zur Verfügung, und zwar mit Ausnahme von dem Punkt, wo nicht auf das Shadowing-Element zugriffen werden kann. Wenn beispielsweise ein `Private`-Element ein Basisklassenelement spiegelt, greift der Code, der nicht über die Berechtigung für den Zugriff auf das `Private`-Element verfügt, anstelle auf das Basisklassenelement zu.|  
|`eventname`|Erforderlich Der Name des Ereignisses; folgt standardmäßigen Variablennamenskonventionen.|  
|`parameterlist`|Optional. Liste der lokalen Variablen, die die Parameter dieses Ereignisses darstellen. Sie müssen die [Parameter Liste](../../../visual-basic/language-reference/statements/parameter-list.md) in Klammern einschließen.|  
|`Implements`|Optional. Gibt an, dass dieses Ereignis ein Ereignis einer Schnittstelle implementiert.|  
|`implementslist`|Erforderlich, wenn `Implements` angegeben wird. Liste der zu implementierenden `Sub`-Prozeduren. Mehrere Prozeduren werden durch Kommas getrennt:<br /><br /> *implementedprocedure* [, *implementedprocedure* ...]<br /><br /> Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:<br /><br /> `interface`.`definedname`<br /><br /> -   `interface`-erforderlich. Name einer Schnittstelle, die von der in dieser Prozedur enthaltenen Klasse oder Struktur implementiert wird.<br />-   `Definedname`-erforderlich. Name, wodurch die Prozedur in `interface` definiert ist. Hierbei muss es sich nicht um demselben Namen wie `name` (den Namen, den dieser Prozedur verwendet, um die definierte Prozedur zu implementieren) handeln.|  
|`Custom`|Erforderlich Als `Custom` deklarierte Ereignisse müssen benutzerdefinierte `AddHandler`-, `RemoveHandler`- und `RaiseEvent`-Accessoren definieren.|  
|`delegatename`|Optional. Der Name eines Delegaten, der die Signatur des Ereignishandlers angibt.|  
|`AddHandler`|Erforderlich Deklariert eine `AddHandler`-Zugriffsmethode, die die auszuführenden Anweisungen angibt, wenn ein Ereignishandler hinzugefügt wird, und zwar entweder explizit mithilfe der `AddHandler`-Anweisung oder implizit mithilfe der `Handles`-Klausel.|  
|`End AddHandler`|Erforderlich Beendet den `AddHandler`-Block.|  
|`value`|Erforderlich Der Parametername.|  
|`RemoveHandler`|Erforderlich Deklariert einen `RemoveHandler`-Accessor, der die auszuführenden Anweisungen angibt, wenn ein Ereignishandler mithilfe der `RemoveHandler`-Anweisung entfernt wird.|  
|`End RemoveHandler`|Erforderlich Beendet den `RemoveHandler`-Block.|  
|`RaiseEvent`|Erforderlich Deklariert einen `RaiseEvent`-Accessor, der die auszuführenden Anweisungen angibt, wenn ein Ereignis mithilfe der `RaiseEvent`-Anweisung ausgelöst wird. Für gewöhnlich wird dadurch eine Liste der Delegaten aufgerufen, die durch die `AddHandler`- und `RemoveHandler`-Accessoren verwaltet werden.|  
|`End RaiseEvent`|Erforderlich Beendet den `RaiseEvent`-Block.|  
|`delegatesignature`|Erforderlich Liste der Parameter, die mit dem Parametern übereinstimmen, die durch das `delegatename`-Delegat erforderlich sind. Sie müssen die [Parameter Liste](../../../visual-basic/language-reference/statements/parameter-list.md) in Klammern einschließen.|  
|`statements`|Optional. Anweisungen, die die Textteile der Methoden `AddHandler`, `RemoveHandler` und `RaiseEvent` enthalten.|  
|`End Event`|Erforderlich Beendet den `Event`-Block.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie nach erfolgter Deklarierung des Ereignisses die Anweisung `RaiseEvent` zum Auslösen des Ereignisses. Ein typisches Ereignis könnte analog zur Darstellung in den folgenden Fragmenten deklariert und ausgelöst werden.  
  
 [!code-vb[VbVbalrEvents#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#13)]  
  
> [!NOTE]
> Sie können Ereignisargumente deklarieren, wie Sie dies bei Argumenten von Prozeduren vornehmen, und zwar mit den folgenden Ausnahmen: Ereignisse können nicht über benannte Argumente, `ParamArray`- oder `Optional`-Argumente verfügen. Ereignisse haben keine Rückgabewerte.  
  
 Zum Verarbeiten eines Ereignisses müssen Sie es mithilfe der Anweisung `Handles` oder `AddHandler` mit einer Ereignishandler-Unterroutine verknüpfen. Die Signaturen der Unterroutine und des Ereignisses müssen übereinstimmen. Zum Verarbeiten eines freigegebenen Ereignisses müssen Sie die Anweisung `AddHandler` verwenden.  
  
 Sie können `Event` nur auf Modulebene verwenden. Dies bedeutet, dass der *Deklarations Kontext* für ein Ereignis eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und nicht eine Quelldatei, ein Namespace, eine Prozedur oder ein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 In den meisten Fällen können Sie zum Deklarieren von Ereignissen die erste Syntax im Syntaxabschnitt dieses Themas verwenden. In einigen Szenarien ist es jedoch erforderlich, dass Sie mehr Kontrolle über das detaillierte Verhalten des Ereignisses verfügen. Die letzte Syntax im Syntaxabschnitt dieses Themas, die das Schlüsselwort `Custom` verwendet, enthält diese Steuerung, indem Ihnen ermöglicht wird, benutzerdefinierte Ereignisse zu definieren. In einem benutzerdefinierten Ereignis geben Sie genau an, was geschieht, wenn ein Ereignishandler mithilfe von Code zum Ereignis hinzugefügt oder daraus entfernt wird oder wenn der Code das Ereignis auslöst. Beispiele hierzu finden Sie unter Gewusst [wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicher](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md) Platz zu sparen, und Gewusst [wie: Deklarieren von benutzerdefinierten Ereignissen, um](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet. Der Code veranschaulicht mehrere der ereignisbezogene Methoden, Eigenschaften und Anweisungen. Dies schließt die `RaiseEvent`-Anweisung mit ein.  
  
 Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler. Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert. Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.  
  
 Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet. Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
 Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an. Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.  
  
 Um dieses Beispiel zu verwenden, öffnen Sie ein neues Windows Forms-Projekt. Fügen Sie dem Hauptformular mit dem Namen `Button1` anschließend eine Schaltfläche mit dem Namen `TextBox1` und ein Textfeld mit dem Namen `Form1` hinzu. Klicken Sie dann mit der rechten Maustaste auf das Formular und dann auf **Code anzeigen** , um den Code-Editor zu öffnen  
  
 Fügen Sie eine `WithEvents`-Variable zum Deklarationsabschnitt der `Form1`-Klasse hinzu:  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
 Fügen Sie den folgenden Code zum Code für `Form1` hinzu. Ersetzen Sie ggf. vorhandene doppelte Prozeduren, beispielsweise `Form_Load` oder `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche **Start**. Im ersten Textfeld werden die Sekunden heruntergezählt. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
> [!NOTE]
> Die `My.Application.DoEvents`-Methode verarbeitet Ereignisse nicht in der gleichen Weise wie das Formular. Damit das Formular die Ereignisse direkt verarbeiten kann, können Sie Multithreading verwenden. Weitere Informationen finden Sie unter [verwaltetes Threading](../../../standard/threading/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
- [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
- [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)

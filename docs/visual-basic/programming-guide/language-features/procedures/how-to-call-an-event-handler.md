---
title: Vorgehensweise beim aufzurufen eines Ereignis Handlers
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3762c79dd3d883ae2ccfe76b335cf98ac87d4246
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89464960"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Vorgehensweise beim aufzurufen eines Ereignis Handlers in Visual Basic

Ein *Ereignis* ist eine Aktion oder ein Vorkommen – z. b. ein Mausklick oder ein Guthaben Limit überschritten –, das von einer Programm Komponente erkannt wird, und für das Sie Code schreiben können, um Antworten zu können. Ein *Ereignishandler* ist der Code, den Sie schreiben, um auf ein Ereignis zu reagieren.

Ein Ereignishandler in Visual Basic ist eine `Sub` Prozedur. Sie werden jedoch normalerweise nicht auf dieselbe Weise aufgerufen wie andere `Sub` Prozeduren. Stattdessen identifizieren Sie die Prozedur als Handler für das-Ereignis. Hierfür können Sie eine [`Handles`](../../../language-reference/statements/handles-clause.md) -Klausel und eine- [`WithEvents`](../../../language-reference/modifiers/withevents.md) Variable oder eine [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md)verwenden. Die Verwendung einer- `Handles` Klausel ist die Standardmethode zum Deklarieren eines Ereignis Handlers in Visual Basic. Dies ist die Methode, mit der die Ereignishandler von den Designern geschrieben werden, wenn Sie in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) programmieren. Die- `AddHandler` Anweisung eignet sich zum dynamischen Ereignisse zur Laufzeit.

Wenn das Ereignis auftritt, ruft Visual Basic automatisch die Ereignishandlerprozedur auf. Jeder Code, der Zugriff auf das Ereignis hat, kann dazu führen, dass er durch Ausführen einer [RaiseEvent-Anweisung](../../../language-reference/statements/raiseevent-statement.md)ausgelöst wird.

Sie können dem gleichen Ereignis mehr als einen Ereignishandler zuordnen. In einigen Fällen können Sie einen Handler von einem Ereignis trennen. Weitere Informationen finden Sie unter [Ereignisse](../events/index.md).

## <a name="call-an-event-handler-using-no-loc-texthandles-and-no-locwithevents"></a>Abrufen eines Ereignis Handlers mithilfe von :::no-loc text="Handles"::: und WithEvents

1. Stellen Sie sicher, dass das Ereignis mit einer [Ereignis Anweisung](../../../language-reference/statements/event-statement.md)deklariert ist.

2. Deklarieren Sie eine Objekt Variable auf Modul-oder Klassenebene mithilfe des [`WithEvents`](../../../language-reference/modifiers/withevents.md) Schlüssel Worts. Die- `As` Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.

3. Fügen Sie in der Deklaration der Ereignis Behandlungs `Sub` Prozedur eine [`Handles`](../../../language-reference/statements/handles-clause.md) -Klausel hinzu, die die `WithEvents` -Variable und den Ereignis Namen angibt.

4. Wenn das Ereignis auftritt, ruft Visual Basic automatisch die `Sub` Prozedur auf. Der Code kann eine- `RaiseEvent` Anweisung verwenden, um das-Ereignis zu treffen.

    Im folgenden Beispiel wird ein Ereignis und eine `WithEvents` Variable definiert, die auf die-Klasse verweist, die das-Ereignis auslöst. Das Ereignis Behandlungs `Sub` Verfahren verwendet eine- `Handles` Klausel, um die Klasse und das Ereignis anzugeben, die es behandelt.

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a>Abrufen eines Ereignis Handlers mithilfe von AddHandler

1. Stellen Sie sicher, dass das-Ereignis mit einer-Anweisung deklariert wird `Event` .

2. Führen Sie eine [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) aus, um die Ereignis Behandlungs `Sub` Prozedur dynamisch mit dem-Ereignis zu verbinden.

3. Wenn das Ereignis auftritt, ruft Visual Basic automatisch die `Sub` Prozedur auf. Der Code kann eine- `RaiseEvent` Anweisung verwenden, um das-Ereignis zu treffen.

    Im folgenden Beispiel wird die-Prozedur mithilfe der [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) im-Konstruktor `OnFormClosing` als Ereignishandler für verknüpft <xref:System.Windows.Forms.Form.FormClosing> .

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    Sie können einen Ereignishandler von einem Ereignis trennen, indem Sie die [RemoveHandler-Anweisung](../../../language-reference/statements/removehandler-statement.md)ausführen.

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](index.md)
- [Sub-Prozeduren](sub-procedures.md)
- [Sub-Anweisung](../../../language-reference/statements/sub-statement.md)
- [AddressOf-Operator](../../../language-reference/operators/addressof-operator.md)
- [Vorgehensweise: Erstellen einer Prozedur](how-to-create-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt](how-to-call-a-procedure-that-does-not-return-a-value.md)

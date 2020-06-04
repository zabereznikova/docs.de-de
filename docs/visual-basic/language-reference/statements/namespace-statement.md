---
title: Namespace-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 0f1ba9a038fc604b6e4ede758891832e087fc096
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404433"
---
# <a name="namespace-statement"></a>Namespace-Anweisung
Deklariert den Namen eines Namespace und bewirkt, dass der Quell Code, der der Deklaration folgt, in diesem Namespace kompiliert wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>Bestandteile  
 Global  
 Optional. Ermöglicht es Ihnen, einen Namespace aus dem Stamm Namespace des Projekts zu definieren. Weitere Informationen finden Sie [unter Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Erforderlich. Ein eindeutiger Name, der den Namespace identifiziert. Muss ein gültiger Visual Basic Bezeichner sein. Weitere Informationen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Optional. Elemente, die den-Namespace bilden. Dazu zählen Enumerationen, Strukturen, Schnittstellen, Klassen, Module, Delegaten und andere Namespaces, sind jedoch nicht darauf beschränkt.  
  
 `End Namespace`  
 Beendet einen- `Namespace` Block.  
  
## <a name="remarks"></a>Bemerkungen  
 Namespaces werden als Organisationssystem verwendet. Sie bieten eine Möglichkeit zum klassifizieren und darstellen von Programmier Elementen, die für andere Programme und Anwendungen verfügbar gemacht werden. Beachten Sie, dass es sich bei einem Namespace nicht um einen *Typ* handelt, der eine Klasse oder Struktur ist – Sie können kein Programmier Element deklarieren, um den Datentyp eines Namespace zu erhalten.  
  
 Alle Programmier Elemente, die nach einer-Anweisung deklariert werden, `Namespace` gehören zu diesem Namespace. Visual Basic werden Elemente weiterhin in den letzten deklarierten Namespace kompiliert, bis entweder eine- `End Namespace` Anweisung oder eine andere-Anweisung gefunden wird `Namespace` .  
  
 Wenn ein Namespace bereits definiert ist, können Sie auch außerhalb des Projekts Programmier Elemente hinzufügen. Zu diesem Zweck verwenden Sie eine- `Namespace` Anweisung, um Visual Basic anzuweisen, Elemente in diesen Namespace zu kompilieren.  
  
 Eine-Anweisung kann `Namespace` nur auf Datei-oder Namespace Ebene verwendet werden. Dies bedeutet, dass der *Deklarations Kontext* für einen Namespace eine Quelldatei oder ein anderer Namespace sein muss und weder eine Klasse noch eine Struktur, ein Modul, eine Schnittstelle oder eine Prozedur sein darf. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).  
  
 Sie können einen Namespace in einem anderen deklarieren. Es gibt keine strikte Beschränkung für die Schachtelungs Ebenen, die Sie deklarieren können. Bedenken Sie jedoch, dass beim Zugreifen auf die im innersten Namespace deklarierten Elemente eine Qualifizierungs Zeichenfolge verwendet werden muss, die alle Namespace Namen in der Schachtelungs Hierarchie enthält.  
  
## <a name="access-level"></a>Zugriffsebene  
 Namespaces werden so behandelt, als ob Sie über eine `Public` Zugriffsebene verfügen. Auf einen Namespace kann von einem beliebigen Speicherort im gleichen Projekt aus zugegriffen werden, von anderen Projekten, die auf das Projekt verweisen, und aus einer Assembly, die aus dem Projekt erstellt wurde.  
  
 Programmier Elemente, die auf Namespace Ebene deklariert werden, d. h. in einem Namespace, aber nicht in einem anderen Element, können über- `Public` oder- `Friend` Zugriff verfügen Wenn nicht angegeben, verwendet die Zugriffsebene eines solchen Elements `Friend` standardmäßig. Elemente, die Sie auf Namespace Ebene deklarieren können, sind Klassen, Strukturen, Module, Schnittstellen, Enumerationen und Delegaten. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).  
  
## <a name="root-namespace"></a>Stamm Namespace  
 Alle Namespace Namen in Ihrem Projekt basieren auf einem *Root-Namespace*. Visual Studio weist den Projektnamen als den Standard-Stammnamespace für den gesamten Code des Projekts zu. Wenn Ihr Projekt beispielsweise den Namen `Payroll`hat, gehören die Programmierelemente zum Namespace `Payroll`. Wenn Sie deklarieren `Namespace funding` , ist der vollständige Name dieses Namespace `Payroll.funding` .  
  
 Wenn Sie einen vorhandenen Namespace in einer-Anweisung angeben möchten `Namespace` , z. b. im Beispiel der generischen List-Klasse, können Sie den Root-Namespace auf einen NULL-Wert festlegen. Klicken Sie hierzu im Menü **Projekt** auf **Projekteigenschaften** , und löschen Sie dann den Eintrag **Root Namespace** , sodass das Feld leer ist. Wenn Sie dies nicht im Beispiel der generischen List-Klasse durchgeführt haben, würde der Visual Basic-Compiler `System.Collections.Generic` als neuen Namespace innerhalb von Project `Payroll` mit dem vollständigen Namen von übernehmen `Payroll.System.Collections.Generic` .  
  
 Alternativ können Sie das- `Global` Schlüsselwort verwenden, um auf Elemente von Namespaces zu verweisen, die außerhalb des Projekts definiert sind. Auf diese Weise können Sie den Projektnamen als Stamm Namespace beibehalten. Dadurch wird die Wahrscheinlichkeit verringert, dass ihre Programmier Elemente versehentlich zusammen mit den vorhandenen Namespaces zusammengeführt werden. Weitere Informationen finden Sie im Abschnitt "globales Schlüsselwort in voll qualifizierten Namen" unter [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 Das- `Global` Schlüsselwort kann auch in einer Namespace-Anweisung verwendet werden. Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren. Weitere Informationen finden Sie im Abschnitt "Global-Schlüsselwort in Namespace-Anweisungen" unter [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 **Problem.** Der Stamm Namespace kann zu unerwarteten Verkettungen von Namespace Namen führen. Wenn Sie Verweise auf Namespaces erstellen, die außerhalb des Projekts definiert sind, kann der Visual Basic Compiler Sie als schsted Namespaces im Stamm Namespace erstellen. In diesem Fall erkennt der Compiler keine Typen, die bereits in den externen Namespaces definiert wurden. Um dies zu vermeiden, legen Sie entweder den Stamm Namespace auf einen NULL-Wert fest, wie unter "Root Namespace" beschrieben, oder verwenden Sie das `Global` Schlüsselwort, um auf Elemente externer Namespaces zuzugreifen.  
  
## <a name="attributes-and-modifiers"></a>Attribute und modifiziererer  
 Attribute können nicht auf einen Namespace angewendet werden. Ein Attribut trägt Informationen zu den Metadaten der Assembly bei, was für Quell Klassifizierungen (z. b. Namespaces) nicht von Bedeutung ist.  
  
 Sie können keinen Zugriffs-oder Prozedur Modifizierer oder andere Modifizierer auf einen Namespace anwenden. Da es sich nicht um einen-Typ handelt, sind diese Modifizierer nicht sinnvoll.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Namespaces deklariert, eine in der anderen.  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden mehrere schsted Namespaces in einer einzelnen Zeile deklariert, und Sie entspricht dem vorherigen Beispiel.  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird auf die-Klasse zugegriffen, die in den vorherigen Beispielen definiert wurde.  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Gerüst einer neuen generischen List-Klasse definiert und dem- <xref:System.Collections.Generic?displayProperty=nameWithType> Namespace hinzugefügt.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Imports-Anweisung (.NET-Namespace und Typ)](imports-statement-net-namespace-and-type.md)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md)

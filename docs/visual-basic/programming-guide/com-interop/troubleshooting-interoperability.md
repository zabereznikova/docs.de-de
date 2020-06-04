---
title: Problembehandlung bei der Interoperabilität
ms.date: 07/20/2015
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability [Visual Basic]
- interoperability, troubleshooting
- COM interop [Visual Basic], troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
ms.openlocfilehash: 0890bac80396feaf37d4ba917c1e3fafb8579981
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396765"
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Problembehandlung bei Interoperabilität (Visual Basic)
Wenn Sie zwischen com und dem verwalteten Code des .NET Framework interagieren, tritt möglicherweise ein oder mehrere der folgenden häufigen Probleme auf.  
  
## <a name="interop-marshaling"></a><a name="vbconinteroperabilitymarshalinganchor1"></a>Interop-Marshalling  
 Manchmal müssen Sie möglicherweise Datentypen verwenden, die nicht Teil der .NET Framework sind. Interop-Assemblys verarbeiten den größten Teil der Arbeit für COM-Objekte, aber Sie müssen möglicherweise die Datentypen steuern, die verwendet werden, wenn verwaltete Objekte für com verfügbar gemacht werden. Beispielsweise müssen Strukturen in Klassenbibliotheken den nicht verwalteten Typ für Zeichen folgen angeben `BStr` , die an COM-Objekte gesendet werden, die von Visual Basic 6,0 und früheren Versionen erstellt wurden. In solchen Fällen können Sie das- <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut verwenden, um zu bewirken, dass verwaltete Typen als nicht verwaltete Typen verfügbar gemacht werden.  
  
## <a name="exporting-fixed-length-strings-to-unmanaged-code"></a><a name="vbconinteroperabilitymarshalinganchor2"></a>Exportieren von Zeichen folgen fester Länge in nicht verwalteten Code  
 In Visual Basic 6,0 und früheren Versionen werden Zeichen folgen als Byte Sequenzen in COM-Objekte exportiert, die keine NULL-Beendigungs Zeichen sind. Aus Gründen der Kompatibilität mit anderen Sprachen schließt Visual Basic .NET beim Exportieren von Zeichen folgen ein Beendigungs Zeichen ein. Die beste Möglichkeit, diese Inkompatibilität zu beheben, besteht darin, Zeichen folgen zu exportieren, die das Beendigungs Zeichen nicht als Arrays von `Byte` oder aufweisen `Char` .  
  
## <a name="exporting-inheritance-hierarchies"></a><a name="vbconinteroperabilitymarshalinganchor3"></a>Exportieren von Vererbungs Hierarchien  
 Verwaltete Klassenhierarchien vereinfachen Sie, wenn Sie als COM-Objekte verfügbar gemacht werden. Wenn Sie z. b. eine Basisklasse mit einem Member definieren und dann die Basisklasse in einer abgeleiteten Klasse erben, die als COM-Objekt verfügbar gemacht wird, können Clients, die die abgeleitete Klasse im COM-Objekt verwenden, die geerbten Member nicht verwenden. Auf Basisklassenmember kann nur über COM-Objekte als Instanzen einer Basisklasse zugegriffen werden. Dies gilt nur, wenn die Basisklasse auch als COM-Objekt erstellt wird.  
  
## <a name="overloaded-methods"></a>Überladene Methoden  
 Obwohl Sie überladene Methoden mit Visual Basic erstellen können, werden Sie von com nicht unterstützt. Wenn eine Klasse, die überladene Methoden enthält, als COM-Objekt verfügbar gemacht wird, werden neue Methodennamen für die überladenen Methoden generiert.  
  
 Stellen Sie sich z. b. eine-Klasse vor, die über zwei über Ladungen der- `Synch` Methode verfügt. Wenn die Klasse als COM-Objekt verfügbar gemacht wird, können die neuen generierten Methodennamen `Synch` und lauten `Synch_2` .  
  
 Die Umbenennung kann für Consumer des COM-Objekts zwei Probleme verursachen.  
  
1. Die generierten Methodennamen werden von Clients möglicherweise nicht erwartet.  
  
2. Die generierten Methodennamen in der-Klasse, die als COM-Objekt verfügbar gemacht werden, können sich ändern, wenn der Klasse oder ihrer Basisklasse neue über Ladungen hinzugefügt werden. Dies kann zu Versions Problemen führen.  
  
 Um beide Probleme zu lösen, geben Sie jeder Methode einen eindeutigen Namen, anstatt überladen zu verwenden, wenn Sie Objekte entwickeln, die als COM-Objekte verfügbar gemacht werden.  
  
## <a name="use-of-com-objects-through-interop-assemblies"></a><a name="vbconinteroperabilitymarshalinganchor4"></a>Verwendung von COM-Objekten über Interop-Assemblys  
 Interop-Assemblys werden fast so verwendet, als würden Sie verwaltete Code Ersetzungen für die von Ihnen dargestellten com-Objekte darstellen. Da es sich jedoch um Wrapper und nicht um tatsächliche com-Objekte handelt, gibt es einige Unterschiede zwischen der Verwendung von Interopassemblys und Standardassemblys Zu diesen Unterschieden gehören das verfügbar machen von Klassen und Datentypen für Parameter und Rückgabewerte.  
  
## <a name="classes-exposed-as-both-interfaces-and-classes"></a><a name="vbconinteroperabilitymarshalinganchor5"></a>Klassen, die als Schnittstellen und Klassen verfügbar gemacht werden  
 Im Unterschied zu Klassen in Standardassemblys werden COM-Klassen in Interopassemblys als Schnittstelle und als Klasse verfügbar gemacht, die die com-Klasse darstellt Der Name der Schnittstelle ist mit der der com-Klasse identisch. Der Name der Interop-Klasse ist mit der der ursprünglichen COM-Klasse identisch, aber mit dem angefügten Wort "Class". Angenommen, Sie verfügen über ein Projekt mit einem Verweis auf eine Interop-Assembly für ein COM-Objekt. Wenn die com-Klasse benannt wird `MyComClass` , zeigen IntelliSense und die Objektkatalog eine Schnittstelle mit dem Namen `MyComClass` und eine Klasse mit dem Namen an `MyComClassClass` .  
  
## <a name="creating-instances-of-a-net-framework-class"></a><a name="vbconinteroperabilitymarshalinganchor6"></a>Erstellen von Instanzen einer .NET Framework-Klasse  
 Im Allgemeinen erstellen Sie eine Instanz einer .NET Framework-Klasse, indem Sie die- `New` Anweisung mit einem Klassennamen verwenden. Eine COM-Klasse, die durch eine Interop-Assembly repräsentiert wird, ist der einzige Fall, in dem Sie die- `New` Anweisung mit einer-Schnittstelle verwenden können. Sofern Sie nicht die com-Klasse mit einer- `Inherits` Anweisung verwenden, können Sie die-Schnittstelle genauso wie eine-Klasse verwenden. Der folgende Code veranschaulicht, wie ein- `Command` Objekt in einem Projekt erstellt wird, das über einen Verweis auf das COM-Objekt der Microsoft ActiveX Data Objects 2,8-Bibliothek verfügt:  
  
 [!code-vb[VbVbalrInterop#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#20)]  
  
 Wenn Sie jedoch die com-Klasse als Basis für eine abgeleitete Klasse verwenden, müssen Sie die Interop-Klasse verwenden, die die com-Klasse darstellt, wie im folgenden Code:  
  
 [!code-vb[VbVbalrInterop#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#21)]  
  
> [!NOTE]
> Interopassemblys implementieren implizit Schnittstellen, die com-Klassen darstellen. Sie sollten nicht versuchen, die- `Implements` Anweisung zu verwenden, um diese Schnittstellen zu implementieren, oder es tritt ein Fehler auf.  
  
## <a name="data-types-for-parameters-and-return-values"></a><a name="vbconinteroperabilitymarshalinganchor7"></a>Datentypen für Parameter und Rückgabewerte  
 Anders als Member von Standardassemblys können Interop-Assemblymember Datentypen aufweisen, die sich von denen in der ursprünglichen Objekt Deklaration unterscheiden. Obwohl Interop-Assemblys com-Typen implizit in kompatible Common Language Runtime Typen konvertieren, sollten Sie auf die Datentypen achten, die von beiden Seiten verwendet werden, um Laufzeitfehler zu vermeiden. Beispielsweise wird in COM-Objekten, die in Visual Basic 6,0 und früheren Versionen erstellt wurden, für Werte des Typs `Integer` der .NET Framework äquivalente Typ angenommen `Short` . Es wird empfohlen, dass Sie die Objektkatalog verwenden, um die Eigenschaften importierter Elemente zu untersuchen, bevor Sie Sie verwenden.  
  
## <a name="module-level-com-methods"></a><a name="vbconinteroperabilitymarshalinganchor8"></a>COM-Methoden auf Modulebene  
 Die meisten COM-Objekte werden verwendet, indem eine Instanz einer com-Klasse mithilfe des `New` -Schlüssel Worts erstellt und dann Methoden des-Objekts aufgerufen werden. Eine Ausnahme von dieser Regel umfasst com-Objekte, die- `AppObj` oder- `GlobalMultiUse` com-Klassen enthalten. Solche Klassen ähneln Methoden auf Modulebene in Visual Basic .NET-Klassen. In Visual Basic 6,0 und früheren Versionen werden implizit Instanzen solcher Objekte erstellt, wenn Sie zum ersten Mal eine ihrer Methoden aufzurufen. Beispielsweise können Sie in Visual Basic 6,0 einen Verweis auf die Microsoft DAO 3,6-Objektbibliothek hinzufügen und die-Methode aufzurufen, `DBEngine` ohne zuerst eine Instanz zu erstellen:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .net erfordert, dass Sie immer Instanzen von COM-Objekten erstellen, bevor Sie Ihre Methoden verwenden können. Um diese Methoden in Visual Basic zu verwenden, deklarieren Sie eine Variable der gewünschten Klasse, und verwenden Sie das New-Schlüsselwort, um das Objekt der Objektvariablen zuzuweisen. Das- `Shared` Schlüsselwort kann verwendet werden, wenn Sie sicherstellen möchten, dass nur eine Instanz der-Klasse erstellt wird.  
  
 [!code-vb[VbVbalrInterop#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#23)]  
  
## <a name="unhandled-errors-in-event-handlers"></a><a name="vbconinteroperabilitymarshalinganchor9"></a>Nicht behandelte Fehler in Ereignis Handlern  
 Ein häufiges Interop-Problem umfasst Fehler in Ereignis Handlern, die Ereignisse behandeln, die von COM-Objekten ausgelöst werden. Solche Fehler werden ignoriert, es sei denn, Sie überprüfen mithilfe der-oder-Anweisungen eine bestimmte `On Error` `Try...Catch...Finally` Das folgende Beispiel ist beispielsweise aus einem Visual Basic .net-Projekt, das einen Verweis auf das COM-Objekt der Microsoft ActiveX Data Objects 2,8-Bibliothek enthält.  
  
 [!code-vb[VbVbalrInterop#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#24)]  
  
 In diesem Beispiel wird wie erwartet ein Fehler ausgelöst. Wenn Sie jedoch das gleiche Beispiel ohne den- `Try...Catch...Finally` Block ausprobieren, wird der Fehler ignoriert, als ob Sie die-Anweisung verwendet haben `OnError Resume Next` . Ohne Fehlerbehandlung schlägt die Division durch Null fehl. Da solche Fehler niemals nicht behandelte Ausnahme Fehler hervorrufen, ist es wichtig, dass Sie eine Ausnahmebehandlung in Ereignis Handlern verwenden, die Ereignisse von COM-Objekten verarbeiten.  
  
### <a name="understanding-com-interop-errors"></a>Informationen zu COM-Interop-Fehlern  
 Ohne Fehlerbehandlung generieren Interop-Aufrufe häufig Fehler, die nur wenige Informationen enthalten. Verwenden Sie nach Möglichkeit die strukturierte Fehlerbehandlung, um weitere Informationen zu auftretenden Problemen bereitzustellen. Dies kann besonders hilfreich sein, wenn Sie Anwendungen debuggen. Beispiel:  
  
 [!code-vb[VbVbalrInterop#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#25)]  
  
 Informationen wie z. b. die Fehlerbeschreibung, HRESULT und die Quelle von com-Fehlern finden Sie unter Untersuchen des Inhalts des Ausnahme Objekts.  
  
## <a name="activex-control-issues"></a><a name="vbconinteroperabilitymarshalinganchor10"></a>ActiveX-Steuerungsprobleme  
 Die meisten ActiveX-Steuerelemente, die mit Visual Basic 6,0 funktionieren, funktionieren ohne Probleme mit Visual Basic .net. Die Haupt Ausnahmen sind Container Steuerelemente oder Steuerelemente, die visuell andere Steuerelemente enthalten. Einige Beispiele für ältere Steuerelemente, die in Visual Studio nicht ordnungsgemäß funktionieren, lauten wie folgt:  
  
- Microsoft Forms 2,0-Frame-Steuerelement  
  
- Auf-ab-Steuerelement, das auch als Dreh Steuerelement bezeichnet wird  
  
- Registerkarten-Steuerelement  
  
 Für nicht unterstützte ActiveX-Steuerungsprobleme gibt es nur wenige Problem Umgehungen. Sie können vorhandene Steuerelemente zu Visual Studio migrieren, wenn Sie den ursprünglichen Quellcode besitzen. Andernfalls können Sie sich mit Softwareanbietern für aktualisierte Informationen informieren. NET-kompatible Versionen von-Steuerelementen zum Ersetzen nicht unterstützter ActiveX-Steuerelemente.  
  
## <a name="passing-readonly-properties-of-controls-byref"></a><a name="vbconinteroperabilitymarshalinganchor11"></a>Übergeben von schreibgeschützten Eigenschaften von Steuerelementen ByRef  
 Visual Basic .NET löst manchmal com-Fehler aus, z. b. "Fehler 0x800A017F CTL_E_SETNOTSUPPORTED", wenn Sie `ReadOnly` Eigenschaften von einigen älteren ActiveX-Steuerelementen als `ByRef` Parameter an andere Prozeduren übergeben. Ähnliche Prozedur Aufrufe von Visual Basic 6,0 führen keinen Fehler aus, und die Parameter werden so behandelt, als hätten Sie Sie als Wert ausgegeben. Die Visual Basic .net-Fehlermeldung gibt an, dass Sie versuchen, eine Eigenschaft zu ändern, die keine Eigenschaften `Set` Prozedur hat.  
  
 Wenn Sie Zugriff auf die aufgerufene Prozedur haben, können Sie diesen Fehler vermeiden, indem Sie das- `ByVal` Schlüsselwort zum Deklarieren von Parametern verwenden, die `ReadOnly` Eigenschaften akzeptieren. Beispiel:  
  
 [!code-vb[VbVbalrInterop#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#26)]  
  
 Wenn Sie keinen Zugriff auf den Quellcode für die aufgerufene Prozedur haben, können Sie die Übergabe der Eigenschaft als Wert erzwingen, indem Sie einen zusätzlichen Satz von Klammern um die aufrufende Prozedur hinzufügen. Beispielsweise können Sie in einem Projekt, das einen Verweis auf das COM-Objekt der Microsoft ActiveX Data Objects 2,8-Bibliothek enthält, Folgendes verwenden:  
  
 [!code-vb[VbVbalrInterop#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#27)]  
  
## <a name="deploying-assemblies-that-expose-interop"></a><a name="vbconinteroperabilitymarshalinganchor12"></a>Bereitstellen von Assemblys, die Interop  
 Das Bereitstellen von Assemblys, die COM-Schnittstellen verfügbar machen, Ein mögliches Problem tritt beispielsweise auf, wenn separate Anwendungen auf dieselbe com-Assembly verweisen. Diese Situation tritt häufig auf, wenn eine neue Version einer Assembly installiert wird und eine andere Anwendung weiterhin die alte Version der Assembly verwendet. Wenn Sie eine Assembly, die eine DLL freigibt, deinstallieren, können Sie Sie versehentlich für die anderen Assemblys nicht verfügbar machen.  
  
 Um dieses Problem zu vermeiden, sollten Sie freigegebene Assemblys im globalen Assemblycache (GAC) installieren und ein Mergemodule für die Komponente verwenden. Wenn Sie die Anwendung nicht im GAC installieren können, sollte Sie in einem Versions spezifischen Unterverzeichnis in CommonFilesFolder installiert werden.  
  
 Assemblys, die nicht freigegeben werden, sollten sich nebeneinander im Verzeichnis mit der aufrufenden Anwendung befinden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [COM-Interop](index.md)
- [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](walkthrough-implementing-inheritance-with-com-objects.md)
- [Inherits Statement](../../language-reference/statements/inherits-statement.md)
- [Globaler Assemblycache](../../../framework/app-domains/gac.md)

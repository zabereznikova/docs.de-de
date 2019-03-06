---
title: Problembehandlung bei Interoperabilität (Visual Basic)
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
ms.openlocfilehash: 197361020ad8c6a88a5fc8617b8e24f420799e14
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377260"
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Problembehandlung bei Interoperabilität (Visual Basic)
Wenn Sie die Interoperabilität zwischen COM und verwalteten Code die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], können Sie eine oder mehrere der folgenden Probleme auftreten.  
  
## <a name="vbconinteroperabilitymarshalinganchor1"></a> Interop-Marshalling  
 In einigen Fällen möglicherweise müssen Sie mit Datentypen, die nicht Teil der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Interop-Assemblys behandeln die meisten Aufgaben für COM-Objekte, aber Sie müssen möglicherweise steuern, die Datentypen, die verwendet werden, wenn verwaltete Objekte für COM verfügbar gemacht werden Strukturen in Klassenbibliotheken müssen angeben, z. B. die `BStr` nicht verwalteter Typ für Zeichenfolgen, die COM-Objekte, die von Visual Basic 6.0 und früheren Versionen erstellten gesendet. In solchen Fällen können Sie die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut dazu führen, dass verwaltete Typen als nicht verwaltete Typen verfügbar gemacht werden.  
  
## <a name="vbconinteroperabilitymarshalinganchor2"></a> Exportieren von Zeichenfolgen mit fester Länge in nicht verwaltetem Code  
 In Visual Basic 6.0 und früher werden die Zeichenfolgen als Bytefolgen ohne abschließendes null-Zeichen auf COM-Objekte exportiert. Kompatibilität mit anderen Sprachen fügt Visual Basic .NET ein abschließendes Zeichen beim Exportieren von Zeichenfolgen. Die beste Möglichkeit, diese Inkompatibilität zu behandeln ist, um Zeichenfolgen zu exportieren, die das Abschlusszeichen als Arrays von hat `Byte` oder `Char`.  
  
## <a name="vbconinteroperabilitymarshalinganchor3"></a> Exportieren von Vererbungshierarchien  
 Verwaltete Klasse, die Hierarchien vereinfachen, wenn als COM-Objekte verfügbar gemacht. Z. B. Wenn Sie mit einem Member eine Basisklasse definieren und die Vererbung der Basisklasse in einer abgeleiteten Klasse, die als COM-Objekt verfügbar gemacht wird, werden Clients, die die abgeleitete Klasse in das COM-Objekt verwenden nicht die geerbten Member verwenden können. Member der Basisklasse können von COM-Objekte nur als Instanzen einer Basisklasse zugegriffen werden, und klicken Sie dann nur, wenn die Basisklasse der Klasse ebenfalls als COM-Objekt erstellt wurde.  
  
## <a name="overloaded-methods"></a>Überladene Methoden  
 Obwohl Sie überladene Methoden mit Visual Basic erstellen können, sind sie nicht von COM unterstützt. Wenn eine Klasse, die überladene Methoden enthält, die als COM-Objekt bereitgestellt wird, werden neue Namen für die überladenen Methoden generiert.  
  
 Betrachten Sie beispielsweise eine Klasse mit zwei Überladungen der `Synch` Methode. Wenn die Klasse als COM-Objekt verfügbar gemacht wird, werden die neuen Namen für die generierte Methode konnte `Synch` und `Synch_2`.  
  
 Die Umbenennung kann dazu führen, dass zwei Probleme für die Nutzer des COM-Objekts.  
  
1.  Clients können nicht die Namen für die generierte Methode erwarten.  
  
2.  Die generierte Methodennamen in der Klasse verfügbar gemacht werden, als COM-Objekt können ändern, wenn die Klasse oder Basisklasse neue Überladungen hinzugefügt werden. Dies kann zu Problemen bei der versionsverwaltung führen.  
  
 Um beide Probleme zu beheben, geben Sie jeder Methode einen eindeutigen Namen ein, anstatt das Überladen zulässt, wenn Sie Objekte entwickeln, die als COM-Objekte verfügbar gemacht werden.  
  
## <a name="vbconinteroperabilitymarshalinganchor4"></a> Verwenden von COM-Objekten über die Interop-Assemblys  
 Sie verwenden die interop-Assemblys, fast so, als ob sie verwalteten Code als Ersatz für die COM-Objekte sind, die sie darstellen. Da sie Wrapper und nicht tatsächliche COM-Objekte sind, bestehen jedoch einige Unterschiede zwischen der Verwendung von interop-Assemblys und standard-Assemblys. Diese betreffen der Offenlegung von Klassen und Datentypen für Parameter und Rückgabewerte.  
  
## <a name="vbconinteroperabilitymarshalinganchor5"></a> Klassen, die verfügbar gemacht werden, als beide Schnittstellen und Klassen  
 Im Gegensatz zu Klassen im standard-Assemblys sind COM-Klassen verfügbar gemacht, in interop-Assemblys als eine Schnittstelle und eine Klasse, die COM-Klasse darstellt. Der Name der Schnittstelle ist identisch mit der COM-Klasse. Der Name der Interop-Klasse ist mit der ursprünglichen COM-Klasse identisch, aber mit dem Wort "Class" angehängt. Nehmen wir beispielsweise an, dass Sie ein Projekt mit einem Verweis auf eine interop-Assembly für COM-Objekt verfügen. Wenn die COM-Klasse heißt `MyComClass`, IntelliSense und Objektkatalog wird gezeigt, eine Schnittstelle, die mit dem Namen `MyComClass` und eine Klasse namens `MyComClassClass`.  
  
## <a name="vbconinteroperabilitymarshalinganchor6"></a> Erstellen von Instanzen von einer .NET Framework-Klasse  
 Im Allgemeinen erstellen Sie eine Instanz von einem [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klasse unter Verwendung der `New` -Anweisung mit einem Klassennamen. Eine COM-Klasse dargestellt, die von einer Interop-Assembly ist in der können Sie diesem einen Fall die `New` -Anweisung mit einer Schnittstelle. Wenn Sie die COM-Klasse mit einer `Inherits` -Anweisung können Sie die Benutzeroberfläche verwenden, wie Sie eine Klasse verwenden. Der folgende Code veranschaulicht, wie eine `Command` Objekt in ein Projekt, das einen Verweis auf das Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt verfügt:  
  
 [!code-vb[VbVbalrInterop#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#20)]  
  
 Wenn Sie die COM-Klasse als Basis für eine abgeleitete Klasse verwenden, müssen Sie jedoch die Interop-Klasse verwenden, die die COM-Klasse, wie im folgenden Code darstellt:  
  
 [!code-vb[VbVbalrInterop#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#21)]  
  
> [!NOTE]
>  Interop-Assemblys implementieren implizit Schnittstellen, die COM-Klassen darstellen. Sie sollten nicht versuchen, verwenden die `Implements` Anweisung zum Implementieren dieser Schnittstellen oder Fehler führt.  
  
## <a name="vbconinteroperabilitymarshalinganchor7"></a> Datentypen für Parameter und Rückgabewerte  
 Im Gegensatz zu den Standardassemblys auf Member möglicherweise interop-Assembly-Member-Datentypen, die sich von denen in der ursprünglichen Deklaration des Objekts unterscheiden. Interop-Assemblys implizit COM-Typen, mit der common Language Runtime kompatible Typen konvertieren, sollten Sie besonders auf die Datentypen Zahlen, die von beiden Seiten verwendet werden, um Laufzeitfehler zu vermeiden. Z. B. in COM-Objekte, die in Visual Basic 6.0 und früheren Versionen, die Werte des Typs erstellte `Integer` davon aus der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] entsprechenden Typ `Short`. Es wird empfohlen, dass Sie den Objektkatalog verwenden, um die Eigenschaften der importierten Elemente zu untersuchen, bevor Sie sie verwenden.  
  
## <a name="vbconinteroperabilitymarshalinganchor8"></a> COM Methoden auf Modulebene  
 Die meisten COM-Objekte werden verwendet, durch Erstellen einer Instanz eines COM-Klasse mit dem `New` -Schlüsselwort und dem anschließenden Aufrufen der Methoden des Objekts. Eine Ausnahme dieser Regel betrifft, COM-Objekten, die enthalten `AppObj` oder `GlobalMultiUse` COM-Klassen. Solche Klassen entsprechen Methoden auf Modulebene in Visual Basic .NET-Klassen. Visual Basic 6.0 und früheren Versionen erstellen implizit Instanzen dieser Objekte für Sie beim ersten, die eine ihrer Methoden aufgerufen werden. Fügen Sie z. B. in Visual Basic 6.0 einen Verweis auf der Microsoft-DAO-3.6-Objektbibliothek und rufen die `DBEngine` -Methode ohne zunächst eine Instanz erstellt:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET ist erforderlich, dass Sie immer Instanzen von COM-Objekten erstellen, bevor Sie deren Methoden verwenden können. Verwenden diese Methoden in Visual Basic, eine Variable für die gewünschte Klasse deklarieren und verwenden das new-Schlüsselwort, um das Objekt die Objektvariable zuweisen. Die `Shared` -Schlüsselwort kann verwendet werden, wenn Sie, um sicherzustellen möchten, dass nur eine Instanz der Klasse erstellt wird.  
  
 [!code-vb[VbVbalrInterop#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#23)]  
  
## <a name="vbconinteroperabilitymarshalinganchor9"></a> Nicht behandelte Fehler in Ereignishandlern  
 Ein häufig auftretendes Problem der Interop-umfasst die Fehler in den Ereignishandlern, die von COM-Objekte ausgelösten Ereignisse behandelt. Diese Fehler werden ignoriert, es sei denn, Sie speziell nach Fehlern, die mithilfe von Suchen `On Error` oder `Try...Catch...Finally` Anweisungen. Beispielsweise ist im folgende Beispiel aus einem Visual Basic .NET-Projekt, das einen Verweis auf das Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt enthält.  
  
 [!code-vb[VbVbalrInterop#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#24)]  
  
 In diesem Beispiel löst einen Fehler an, wie erwartet. Jedoch wenn Sie, dasselbe Beispiel ohne versuchen die `Try...Catch...Finally` Block, der Fehler wird ignoriert, als ob Sie verwendet die `OnError Resume Next` Anweisung. Ohne Fehlerbehandlung wird die Division durch 0 (null) im Hintergrund fehlschlägt. Da solche Fehler niemals Fehler für nicht behandelte Ausnahme auslöst, ist es wichtig, dass Sie eine Form der Behandlung von Ausnahmen in Ereignishandlern, das Behandeln von Ereignissen von COM-Objekte verwenden.  
  
### <a name="understanding-com-interop-errors"></a>Grundlegendes zu COM-Interop-Fehlern  
 Ohne Fehlerbehandlung generieren Interop-Aufrufe häufig Fehler, die wenig Informationen bereitstellen. Verwenden Sie nach Möglichkeit strukturierte Fehlerbehandlung, um weitere Informationen zu Problemen zu ermöglichen, wenn sie auftreten. Dies kann besonders hilfreich sein, wenn Sie Anwendungen Debuggen. Zum Beispiel:  
  
 [!code-vb[VbVbalrInterop#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#25)]  
  
 Sie finden Informationen wie z. B. die fehlerbeschreibung, HRESULT und die Quelle des COM-Fehler, durch den Inhalt des Ausnahmeobjekts untersuchen.  
  
## <a name="vbconinteroperabilitymarshalinganchor10"></a> ActiveX-Steuerelement gibt.  
 Die meisten ActiveX-Steuerelemente, die mit Visual Basic 6.0 arbeiten, die ohne schwierigkeiten mit Visual Basic .NET arbeiten werden. Die wichtigsten Ausnahmen sind Listencontainer-Steuerelemente oder Steuerelemente, die visuell auf andere Steuerelemente enthalten. Einige Beispiele für ältere Steuerelemente, die mit Visual Studio nicht ordnungsgemäß funktionieren, sind wie folgt:  
  
-   Microsoft Forms 2.0-Frame-Steuerelement  
  
-   Auf-ab-Steuerelement, auch bekannt als das Drehfeld-Steuerelement  
  
-   Sheridan Registerkarten-Steuerelement  
  
 Es sind nur einige problemumgehungen für nicht unterstützte ActiveX-Steuerelement-Probleme. Sie können vorhandene Steuerelemente in Visual Studio migrieren, wenn Sie den ursprünglichen Quellcode besitzen. Andernfalls können Sie mit dem Softwareanbieter überprüfen, für aktualisiert. NET-kompatiblen Versionen von Steuerelementen ersetzt nicht die ActiveX-Steuerelemente unterstützt.  
  
## <a name="vbconinteroperabilitymarshalinganchor11"></a> Übergeben von ReadOnly-Eigenschaften der Steuerelemente ByRef  
 Visual Basic .NET in einigen Fällen löst COM-Fehler wie z. B. "Fehler 0x800A017F CTL_E_SETNOTSUPPORTED", wenn übergeben werden `ReadOnly` Eigenschaften, die ältere ActiveX-Steuerelemente als `ByRef` Parameter anderer Prozeduren. Ähnlich wie Prozeduraufrufe von Visual Basic 6.0 ist kein Fehler ausgelöst, und die Parameter behandelt, als ob Sie sie als Wert übergeben. Die Visual Basic .NET Fehlermeldung gibt an, dass Sie versuchen, eine Eigenschaft zu ändern, die nicht über eine Eigenschaft verfügt `Set` Verfahren.  
  
 Wenn Sie den Zugriff auf die aufgerufene Prozedur verfügen, können Sie verhindern diesen Fehler mithilfe der `ByVal` Schlüsselwort, um Parameter zu deklarieren, die akzeptieren `ReadOnly` Eigenschaften. Zum Beispiel:  
  
 [!code-vb[VbVbalrInterop#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#26)]  
  
 Wenn Sie nicht über Zugriff auf den Quellcode für die aufgerufene Prozedur verfügen, können Sie die Eigenschaft als Wert übergeben werden, indem Sie einen zusätzlichen Satz von Klammern um die aufrufende Prozedur hinzufügen erzwingen. Z. B. in einem Projekt, das einen Verweis auf das Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt verfügt, können Sie:  
  
 [!code-vb[VbVbalrInterop#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#27)]  
  
## <a name="vbconinteroperabilitymarshalinganchor12"></a> Bereitstellen von Assemblys, die Interop verfügbar machen.  
 Bereitstellen von Assemblys, die COM-Schnittstellen verfügbar machen, stellt einige spezielle Herausforderungen. Beispielsweise tritt auf, ein potenzielles Problem, wenn separate Anwendungen die gleiche COM-Assembly verweisen. Dies ist üblich, wenn eine neue Version einer Assembly installiert ist, und eine andere Anwendung wird weiterhin die alte Version der Assembly verwendet. Wenn Sie eine Assembly zu deinstallieren, die eine DLL-Datei teilt können Sie versehentlich es nicht verfügbar für die andere Assemblys vornehmen.  
  
 Um dieses Problem zu vermeiden, sollten Sie freigegebene Assemblys zum globalen Assemblycache (GAC) installieren und verwenden ein Mergemodul für die Komponente. Wenn Sie die Anwendung im GAC installieren können, sollte es in einem Unterverzeichnis hängt von der Version des CommonFilesFolder installiert werden.  
  
 Assemblys, die nicht gemeinsam genutzt werden sollten im Verzeichnis mit der aufrufenden Anwendung nebeneinander befinden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Globaler Assemblycache](../../../framework/app-domains/gac.md)

---
title: "Problembehandlung bei Interoperabilität (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 988d07fe08a6a78ae295d13f694c55a3b8f9d2e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Problembehandlung bei Interoperabilität (Visual Basic)
Wenn Sie COM- und des verwalteten Codes der Zusammenwirken der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], können Sie eine oder mehrere der folgenden Probleme auftreten.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a>Interop-Marshalling  
 In einigen Fällen müssen unter Umständen Datentypen verwenden, die nicht Teil der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Interop-Assemblys behandeln die meisten Aufgaben für COM-Objekte, aber möglicherweise müssen Sie die Daten zu steuern, die verwendet werden, wenn verwaltete Objekte für COM verfügbar gemacht werden Strukturen in Klassenbibliotheken müssen angeben, z. B. die `BStr` nicht verwalteten Typ für Zeichenfolgen an COM-Objekten, die von Visual Basic 6.0 und früheren Versionen erstellt gesendet. In solchen Fällen können Sie die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut, das dazu führen, dass verwaltete Typen als nicht verwaltete Typen verfügbar gemacht werden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a>Exportieren von Zeichenfolgen mit fester Länge zu nicht verwaltetem Code  
 In Visual Basic 6.0 und früheren Versionen werden Zeichenfolgen als Bytefolgen ohne abschließendes null-Zeichen in COM-Objekte exportiert. Um die Kompatibilität mit anderen Sprachen fügt Visual Basic .NET ein abschließendes Zeichen beim Exportieren von Zeichenfolgen. Die beste Möglichkeit, diese Inkompatibilität zu behandeln ist, Zeichenfolgen zu exportieren, die das Abschlusszeichen als Arrays von fehlender `Byte` oder `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a>Ausführende Vererbungshierarchien  
 Verwalteter Klassen Hierarchien vereinfachen, wenn als COM-Objekte verfügbar gemacht. Z. B. Wenn Sie eine Basisklasse mit einem Member definieren und dann erben die Basisklasse in einer abgeleiteten Klasse, die als COM-Objekt verfügbar gemacht wird, werden Clients, die in der COM-Objekt die abgeleitete Klasse verwenden nicht die geerbten Member verwenden können. Member der Basisklasse können von COM-Objekte nur als Instanzen einer Basisklasse zugegriffen werden und dann nur, wenn die Basisklasse ebenfalls als COM-Objekt erstellt wurde.  
  
## <a name="overloaded-methods"></a>Überladene Methoden  
 Sie können jedoch überladene Methoden mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], sie werden nicht von COM unterstützt. Wenn eine Klasse, die überladene Methoden enthält, die als COM-Objekt verfügbar ist, werden neue Namen von Methoden für überladenen Methoden generiert.  
  
 Betrachten Sie beispielsweise eine Klasse mit zwei Überladungen der `Synch` Methode. Wenn die Klasse als COM-Objekt verfügbar gemacht wird, ist der neu generierten Methodennamen möglicherweise `Synch` und `Synch_2`.  
  
 Die Umbenennung kann dazu führen, dass zwei Probleme für Consumer des COM-Objekts.  
  
1.  Clients können die generierten Methodennamen nicht erwarten.  
  
2.  Die generierte Methodennamen in der Klasse als COM-Objekt verfügbar gemachte können ändern, wenn neue Überladungen der Klasse oder seine Basisklasse hinzugefügt werden. Dies kann Versionsprobleme verursachen.  
  
 Um beide Probleme zu beheben, weisen Sie jeder Methode einen eindeutigen Namen ein, anstatt Sie mithilfe des Überladens, wenn Sie Objekte entwickeln, die als COM-Objekte verfügbar gemacht werden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a>Verwenden von COM-Objekten über die Interop-Assemblys  
 Sie verwenden die Interop-Assemblys, fast so, als ob sie verwalteten Code als Ersatz für die COM-Objekte sind, die sie darstellen. Da diese Wrapper und keine eigentlichen COM-Objekte sind, bestehen jedoch einige Unterschiede zwischen der Verwendung von Interop-Assemblys und Standardassemblys. Dieser Unterschied umfassen des Offenlegen von Klassen und Datentypen für Parameter und Rückgabewerte.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a>Klassen, die verfügbar gemacht werden, als beide Schnittstellen und Klassen  
 Im Gegensatz zu Klassen in Standardassemblys werden Klassen für COM verfügbar gemacht, in Interop-Assemblys als eine Schnittstelle und eine Klasse, die COM-Klasse darstellt. Der Name der Schnittstelle ist identisch mit der COM-Klasse. Der Name der Interop-Klasse wird mit der ursprünglichen COM-Klasse identisch, aber mit dem Wort "Class" angehängt. Nehmen Sie beispielsweise an, dass Sie ein Projekt mit einem Verweis auf eine Interop-Assembly für COM-Objekt verfügen. Wenn die COM-Klasse heißt `MyComClass`, IntelliSense und den Objektkatalog Anzeigen eine Schnittstelle mit dem Namen `MyComClass` und eine Klasse namens `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a>Erstellen von Instanzen einer .NET Framework-Klasse  
 Im Allgemeinen erstellen Sie eine Instanz von einem [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klasse unter Verwendung der `New` Anweisung durch einen Klassennamen. Eine COM-Klasse dargestellt, die von einer Interop-Assembly ist eine Groß-/Kleinschreibung, die in der können Sie die `New` -Anweisung mit einer Schnittstelle. Außer bei der COM-Klasse mit einer `Inherits` -Anweisung können Sie die Benutzeroberfläche verwenden, wie Sie eine Klasse. Der folgende Code veranschaulicht, wie ein `Command` Objekt in ein Projekt, das einen Verweis auf das Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt enthält:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Wenn Sie die COM-Klasse als Basis für eine abgeleitete Klasse verwenden, müssen Sie die Interop-Klasse verwenden, die COM-Klasse, wie im folgenden Code darstellt:  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Interop-Assemblys implementiert implizit Schnittstellen, die COM-Klassen darstellen. Sie sollten nicht versuchen, verwenden Sie die `Implements` Anweisung zum Implementieren dieser Schnittstellen oder Fehler führt.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a>Datentypen für Parameter und Rückgabewerte  
 Im Gegensatz zu Membern von Standardassemblys möglicherweise Interop-Assembly-Member-Datentypen, die unterscheiden sich von denjenigen, die in der ursprünglichen Deklaration des Objekts verwendet. Interop-Assemblys, mit der common Language Runtime kompatible Typen implizit COM-Typen konvertieren, beachten Sie besonders auf die Datentypen, die von beiden Seiten verwendet werden, um Laufzeitfehler zu vermeiden. Beispielsweise ist in COM-Objekte, die in Visual Basic 6.0 und früheren Versionen, die Werte des Typs erstellt `Integer` gehen davon aus den [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] entspricht der Typ `Short`. Es wird empfohlen, dass Sie den Objektkatalog verwenden, um untersuchen Sie die Eigenschaften der importierten Elemente ein, bevor Sie sie verwenden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a>COM Methoden auf Modulebene  
 Die meisten COM-Objekte werden verwendet, durch das Erstellen einer Instanz eines COM-Klasse unter Verwendung der `New` -Schlüsselwort und dem anschließenden Aufrufen der Methoden des Objekts. Eine Ausnahme dieser Regel betrifft COM-Objekte, die enthalten `AppObj` oder `GlobalMultiUse` COM-Klassen. Solche Klassen ähneln Methoden auf Modulebene in Visual Basic .NET Klassen. Visual Basic 6.0 und früheren Versionen erstellen implizit Instanzen der betroffenen Objekte für Sie erstmalig, die eine ihrer Methoden aufgerufen werden. Fügen Sie z. B. in Visual Basic 6.0 einen Verweis auf die Microsoft DAO 3.6-Objektbibliothek, und rufen die `DBEngine` Methode ohne zunächst eine Instanz erstellt:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET erfordert, dass Sie immer Instanzen von COM-Objekten erstellen, bevor Sie deren Methoden verwenden können. Diese Methoden in Visual Basic verwenden, deklarieren Sie eine Variable, der die gewünschte Klasse aus, und verwenden das new-Schlüsselwort, um die Objektvariable zuweisen. Die `Shared` -Schlüsselwort kann verwendet werden, wenn Sie sicherstellen möchten, dass nur eine Instanz der Klasse erstellt wird.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a>Nicht behandelte Fehler in den Ereignishandlern  
 Ein häufig auftretendes Problem der Interop-umfasst Fehler im Ereignishandler, die von COM-Objekten ausgelöste Ereignisse behandeln. Diese Fehler werden ignoriert, es sei denn, Sie prüfen Sie insbesondere nach Fehlern, die mit `On Error` oder `Try...Catch...Finally` Anweisungen. Beispielsweise wird im folgende Beispiel aus einem Visual Basic .NET-Projekt, das einen Verweis auf das Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt enthält.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 In diesem Beispiel löst einen Fehler aus, wie erwartet. Jedoch wenn Sie, die dasselbe Beispiel ohne versuchen das `Try...Catch...Finally` Block, der Fehler wird ignoriert, als ob Sie verwendet die `OnError Resume Next` Anweisung. Ohne Fehlerbehandlung schlägt fehl, die Division durch 0 (null) im Hintergrund. Da solche Fehler nie Fehler nicht behandelte Ausnahme auslöst, ist es wichtig, dass Sie verwenden bestimmt eine Form der Ausnahmebehandlung im Ereignishandler, die Ereignisse aus COM-Objekte zu verarbeiten.  
  
### <a name="understanding-com-interop-errors"></a>Grundlegendes zu COM-Interop-Fehler  
 Ohne Fehlerbehandlung generieren Interop-Aufrufe häufig Fehler, die wenig Informationen bereitstellen. Verwenden Sie nach Möglichkeit strukturierte Fehlerbehandlung, um weitere Informationen zu Problemen bereitstellen, wenn sie auftreten. Dies kann besonders hilfreich sein, wenn Sie Anwendungen Debuggen. Zum Beispiel:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 Sie können Informationen wie die fehlerbeschreibung, HRESULT und die Quelle der COM-Fehler untersuchen des Inhalts des Ausnahmeobjekts finden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a>ActiveX-Steuerelement-Probleme  
 Die meisten ActiveX-Steuerelemente, die mit Visual Basic 6.0 arbeiten werden mit Visual Basic .NET arbeiten, ohne Probleme. Die wichtigsten Ausnahmen sind Container oder Steuerelemente, die visuell andere Steuerelemente enthalten. Einige Beispiele für ältere Steuerelemente, die mit nicht ordnungsgemäß funktionieren [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] lauten wie folgt:  
  
-   Microsoft Forms 2.0-Frame-Steuerelement  
  
-   Auf-ab-Steuerelement, auch bekannt als das Drehfeld-Steuerelement  
  
-   Sheridan Registerkarten-Steuerelement  
  
 Es gibt nur wenige problemumgehungen für nicht unterstützte ActiveX-Steuerelement-Probleme. Sie können vorhandene Steuerelementen zu migrieren [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Wenn Sie den ursprünglichen Quellcode besitzen. Überprüfen Sie andernfalls können Sie mit dem Softwareanbieter für aktualisiert. NET-kompatiblen Versionen von Steuerelementen ersetzen unterstützt ActiveX-Steuerelemente.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a>Übergeben von ReadOnly-Eigenschaften der Steuerelemente ByRef  
 Visual Basic .NET in einigen Fällen löst COM-Fehler, z. B. "Fehler 0x800A017F CTL_E_SETNOTSUPPORTED", wenn übergeben werden `ReadOnly` Eigenschaften von einigen älteren ActiveX-Steuerelementen als `ByRef` Parameter anderer Prozeduren. Ähnliche Prozeduraufrufe aus Visual Basic 6.0 lösen keine Fehler, und die Parameter werden behandelt, als ob Sie sie als Wert übergeben. Die Visual Basic .NET Fehlermeldung gibt an, dass Sie versuchen, eine Eigenschaft zu ändern, die über keine Eigenschaft `Set` Prozedur.  
  
 Wenn Sie die aufgerufene Prozedur können zugreifen, können Sie diesen Fehler verhindern, mithilfe der `ByVal` Schlüsselwort, um Parameter zu deklarieren, die akzeptieren `ReadOnly` Eigenschaften. Zum Beispiel:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Wenn Sie keinen Zugriff auf den Quellcode für die aufgerufene Prozedur haben, können Sie die Eigenschaft als Wert übergeben werden, indem Sie einen zusätzlichen Satz von Klammern um die aufrufende Prozedur hinzufügen erzwingen. Z. B. in einem Projekt, das einen Verweis auf das Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt enthält, können Sie:  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a>Bereitstellen von Assemblys, die Interop verfügbar machen.  
 Bereitstellen von Assemblys, die COM-Schnittstellen verfügbar machen, stellt einige eindeutige Herausforderungen. Beispielsweise tritt ein mögliches Problem beim separate Anwendungen die gleiche COM-Assembly verweisen. Diese Situation ist üblich, wenn eine neue Version einer Assembly installiert wird und eine andere Anwendung wird weiterhin die alte Version der Assembly. Wenn Sie eine Assembly zu deinstallieren, die gemeinsam eine DLL können Sie unbeabsichtigt nicht verfügbar für die andere Assemblys erleichtern.  
  
 Um dieses Problem zu vermeiden, sollten Sie freigegebene Assemblys zum globalen Assemblycache (GAC) installieren und verwenden ein Mergemodul für die Komponente. Wenn Sie die Anwendung im GAC installieren können, sollten sie in einem Unterverzeichnis versionsspezifische auf CommonFilesFolder installiert werden.  
  
 Assemblys, die nicht gemeinsam genutzt werden, sollten im Verzeichnis mit der aufrufenden Anwendung nebeneinander befinden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Globaler Assemblycache](../../../framework/app-domains/gac.md)

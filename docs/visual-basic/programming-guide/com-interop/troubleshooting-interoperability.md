---
title: "Problembehandlung bei Interoperabilität (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability
- interoperability, troubleshooting
- COM interop, troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: cbc37638ed5c57b94356c2d189f36b66202ceba5
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-interoperability-visual-basic"></a>Problembehandlung bei Interoperabilität (Visual Basic)
Wenn Sie Interoperabilität zwischen COM und verwaltetem Code von der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], eine oder mehrere der folgenden Probleme auftreten können.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a>Interop-Marshalling  
 Von Zeit zu Zeit müssen unter Umständen Datentypen verwenden, die nicht Teil der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Interop-Assemblys behandeln die meisten Aufgaben für COM-Objekte, jedoch müssen Sie möglicherweise die Daten steuern, die verwendet werden, wenn verwaltete Objekte für COM verfügbar gemacht werden Strukturen in Klassenbibliotheken müssen z. B. Angeben der `BStr` nicht verwalteten Typ auf Zeichenfolgen, die von Visual Basic 6.0 und früheren Versionen erstellte COM-Objekte gesendet. In solchen Fällen können Sie die <xref:System.Runtime.InteropServices.MarshalAsAttribute>Attribut, damit verwaltete Typen als nicht verwaltete Typen verfügbar gemacht werden.</xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a>Exportieren von Zeichenfolgen fester Länge in nicht verwaltetem Code  
 In Visual Basic 6.0 und früheren Versionen werden Zeichenfolgen als Bytefolgen ohne abschließendes null-Zeichen in COM-Objekte exportiert. Für die Kompatibilität mit anderen Sprachen [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] Fügt ein abschließendes Zeichen beim Exportieren von Zeichenfolgen. Die beste Möglichkeit, diese Inkompatibilität zu beheben ist, Zeichenfolgen, können exportieren das Endzeichen der als Arrays von `Byte` oder `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a>Exportieren von Vererbungshierarchien  
 Verwalteter Klassen Hierarchien gehen beim Offenlegen als COM-Objekte verfügbar gemacht. Z. B. Wenn Sie eine Basisklasse mit einem Member definieren und dann erben die Basisklasse in einer abgeleiteten Klasse, die als COM-Objekt verfügbar gemacht wird, werden Clients, die im COM-Objekt die abgeleitete Klasse verwenden nicht die geerbten Member verwenden können. Member der Basisklasse können von COM-Objekten nur als Instanzen einer Basisklasse zugegriffen werden, und klicken Sie dann nur, wenn die Basisklasse ebenfalls als COM-Objekt erstellt wird.  
  
## <a name="overloaded-methods"></a>Überladene Methoden  
 Sie können jedoch überladene Methoden mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], werden sie von COM nicht unterstützt Wenn eine Klasse, die überladene Methoden enthält, die als COM-Objekt verfügbar ist, werden für die überladenen Methoden neue Methodennamen generiert.  
  
 Betrachten Sie beispielsweise eine Klasse mit zwei Überladungen der `Synch` Methode. Wenn die Klasse als COM-Objekt verfügbar gemacht wird, kann die neu generierten Methodennamen `Synch` und `Synch_2`.  
  
 Die Umbenennung kann dazu führen, dass zwei Probleme für Consumer des COM-Objekts.  
  
1.  Clients können die generierten Methodennamen nicht erwarten.  
  
2.  Die generierten Methodennamen in der Klasse als COM-Objekt verfügbar gemacht können ändern, wenn neue Überladungen der Klasse oder der Basisklasse hinzugefügt werden. Dies kann Versionsprobleme verursachen.  
  
 Um beide Probleme zu beheben, geben Sie jeder Methode einen eindeutigen Namen, anstatt Sie mithilfe der Überladung, wenn Sie Objekte entwickeln, die als COM-Objekte verfügbar gemacht werden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a>Verwenden von COM-Objekten über Interop-Assemblys  
 Verwenden Sie Interop-Assemblys, fast so, als ob sie verwalteten Code als Ersatz für die COM-Objekte sind, die sie darstellen. Da sie Wrapper und keine eigentlichen COM-Objekte sind, bestehen jedoch einige Unterschiede zwischen der Verwendung von Interop-Assemblys und Standardassemblys. Diese betreffen der Offenlegung von Klassen und Datentypen für Parameter und Rückgabewerte.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a>Klassen, die verfügbar gemacht werden, als beide Schnittstellen und Klassen  
 Im Gegensatz zu Klassen in Standardassemblys werden COM-Klassen verfügbar gemacht, in Interop-Assemblys als eine Schnittstelle und eine Klasse, die COM-Klasse darstellt. Der Name der Schnittstelle ist identisch mit dem der COM-Klasse. Der Name der Interop-Klasse ist identisch mit der ursprünglichen COM-Klasse mit dem Wort "Class" angefügt. Nehmen wir beispielsweise an, dass Sie ein Projekt mit einem Verweis auf eine Interop-Assembly für COM-Objekt verfügen. Wenn die COM-Klasse heißt `MyComClass`, IntelliSense und im Objektkatalog Anzeigen eine Schnittstelle namens `MyComClass` und eine Klasse namens `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a>Erstellen von Instanzen einer .NET Framework-Klasse  
 Im Allgemeinen erstellen Sie eine Instanz von einer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] -Klasse unter Verwendung der `New` -Anweisung mit einem Namen. Eine durch eine Interop-Assembly dargestellte COM-Klasse ist, verwenden Sie die `New` -Anweisung mit einer Schnittstelle. Nur beim verwenden die COM-Klasse mit einer `Inherits` -Anweisung können Sie die Schnittstelle wie eine Klasse verwenden. Der folgende Code veranschaulicht, wie ein `Command` Objekt in ein Projekt, das einen Verweis auf die Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt hat:  
  
 [!code-vb[VbVbalrInterop&20;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Wenn Sie die COM-Klasse als Basis für eine abgeleitete Klasse verwenden, müssen Sie die Interop-Klasse verwenden, die für die COM-Klasse, wie im folgenden Code:  
  
 [!code-vb[VbVbalrInterop&21;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Interop-Assemblys implementieren implizit Schnittstellen, die COM-Klassen darstellen. Sie sollten nicht versuchen, verwenden Sie die `Implements` Anweisung zum Implementieren dieser Schnittstellen führt.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a>Datentypen für Parameter und Rückgabewerte  
 Im Gegensatz zu Membern von Standardassemblys möglicherweise Interop-Assemblies-Datentypen, die von denen in der ursprünglichen Deklaration des Objekts abweichen. Zwar Interop-Assemblys für COM-Typen implizit in mit der common Language Runtime kompatible Typen konvertiert, achten Sie besonders auf die Datentypen, die von beiden Seiten verwendet werden, um Laufzeitfehler zu vermeiden. Z. B. in COM-Objekte, die in Visual Basic 6.0 und früheren Versionen, die Werte des Typs erstellt `Integer` nehmen Sie an der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] entsprechenden Typ `Short`. Es wird empfohlen, dass Sie den Objektkatalog verwenden, um die Merkmale importierter Member zu untersuchen, bevor Sie sie verwenden.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a>COM Methoden auf Modulebene  
 Die meisten COM-Objekte wird durch Erstellen einer Instanz eines COM-Klasse mit dem `New` -Schlüsselwort und dem anschließenden Aufrufen der Methoden des Objekts. Eine Ausnahme dieser Regel betrifft COM-Objekte, die enthalten `AppObj` oder `GlobalMultiUse` COM-Klassen. Solche Klassen entsprechen den Methoden auf Modulebene in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] Klassen. Visual Basic 6.0 und früheren Versionen erstellen implizit Instanzen solcher Objekte zur ersten, die eine ihrer Methoden aufgerufen werden. Fügen Sie z. B. in Visual Basic 6.0 einen Verweis auf die Microsoft DAO 3.6-Objektbibliothek und rufen Sie die `DBEngine` Methode ohne zunächst eine Instanz erstellt:  
  
```  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]erfordert, dass Sie immer Instanzen von COM-Objekten erstellen, bevor Sie deren Methoden verwenden können. Diese Methoden in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], deklarieren Sie eine Variable der gewünschten Klasse, und verwenden Sie das new-Schlüsselwort, das Objekt der Objektvariablen zuzuweisen. Das `Shared` -Schlüsselwort kann verwendet werden, wenn Sie sicherstellen möchten, dass nur eine Instanz der Klasse erstellt wird.  
  
 [!code-vb[VbVbalrInterop&23;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a>Nicht behandelte Fehler im Ereignishandler  
 Ein häufiges Interop-Problem umfasst die Fehler im Ereignishandler, die von COM-Objekten ausgelöste Ereignisse behandeln. Solche Fehler werden ignoriert, es sei denn, Sie prüfen Sie insbesondere für Fehler bei der Verwendung `On Error` oder `Try...Catch...Finally` Anweisungen. Z. B. das folgende Beispiel stammt aus einer [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] -Projekt, das einen Verweis auf das Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt enthält.  
  
 [!code-vb[VbVbalrInterop&#24;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 In diesem Beispiel löst einen Fehler aus, wie erwartet. Jedoch wenn Sie, dasselbe Beispiel ohne versuchen den `Try...Catch...Finally` Block, der Fehler wird ignoriert, wie wenn Sie die `OnError Resume Next` Anweisung. Ohne Fehlerbehandlung schlägt die Division durch&0; (null) im Hintergrund fehl. Da solche Fehler niemals Fehler nicht behandelte Ausnahme auslöst, ist es wichtig, dass Sie eine Form der Ausnahmebehandlung in Ereignishandler für die Behandlung von Ereignissen COM-Objekte verwenden.  
  
### <a name="understanding-com-interop-errors"></a>Grundlegendes zu COM-Interop-Fehler  
 Ohne Fehlerbehandlung generieren Interop-Aufrufe häufig Fehler, die wenig Informationen liefern. Verwenden Sie nach Möglichkeit strukturierte Fehlerbehandlung bieten weitere Informationen zu Problemen, bei deren auftreten. Dies kann besonders hilfreich sein, beim Debuggen von ASP.NET-Webanwendungen. Zum Beispiel:  
  
 [!code-vb[VbVbalrInterop&#25;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 Erhalten Sie Informationen wie die Beschreibung, HRESULT und die Quelle der COM-Fehler durch den Inhalt des Ausnahmeobjekts untersuchen.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a>ActiveX-Steuerelement-Probleme  
 Die meisten ActiveX-Steuerelemente, die mit Visual Basic 6.0 arbeiten mit [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] problemlos. Die wichtigsten Ausnahmen sind Container oder Steuerelemente, die visuell andere Steuerelemente enthalten. Einige Beispiele für ältere Steuerelemente, die in nicht ordnungsgemäß funktionieren [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] lauten wie folgt:  
  
-   Microsoft Forms 2.0-Frame-Steuerelement  
  
-   Auf-ab-Steuerelement, auch bekannt als das Drehfeld-Steuerelement  
  
-   Schreiber Registerkarten-Steuerelement  
  
 Es gibt nur wenige Lösungsmöglichkeiten für nicht unterstützte ActiveX-Steuerelement-Probleme. Sie können vorhandene Steuerelemente migrieren [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Wenn Sie den ursprünglichen Quellcode besitzen. Überprüfen Sie andernfalls können Sie mit Software-Anbietern für aktualisiert. NET-kompatiblen Versionen von Steuerelementen ersetzen nicht die ActiveX-Steuerelemente unterstützt.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a>Die ReadOnly-Eigenschaften der Steuerelemente ByRef übergeben  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]Löst manchmal COM-Fehler, z. B. "Error 0x800A017F CTL_E_SETNOTSUPPORTED" aus, wenn Sie übergeben `ReadOnly` Eigenschaften älterer ActiveX-Steuerelemente als `ByRef` Parameter an andere Prozeduren. Ähnliche Prozeduraufrufe aus Visual Basic 6.0 lösen keinen Fehler, und die Parameter werden behandelt, als ob Sie sie nach Wert übergeben. Die Fehlermeldung finden Sie unter in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] ist das COM-Objekt, das meldet, dass Sie versuchen, eine Eigenschaft zu ändern, die nicht über eine Eigenschaft verfügt `Set` Verfahren.  
  
 Wenn Sie die aufgerufene Prozedur können zugreifen, können Sie diesen Fehler verhindern, mithilfe der `ByVal` Schlüsselwort Parameter zu deklarieren, akzeptieren `ReadOnly` Eigenschaften. Beispiel:  
  
 [!code-vb[VbVbalrInterop&#26;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Wenn Sie keinen Zugriff auf den Quellcode für die aufgerufene Prozedur können Sie die Eigenschaft als Wert übergeben wird, durch hinzufügen einen zusätzlichen Satz von Klammern die aufrufende Prozedur erzwingen. Z. B. in einem Projekt, das einen Verweis auf die Microsoft ActiveX Data Objekte 2.8-Bibliothek COM-Objekt verfügt, können Sie:  
  
 [!code-vb[VbVbalrInterop&#27;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a>Bereitstellen von Assemblys, die Interop verfügbar machen  
 Bereitstellen von Assemblys, die COM-Schnittstellen verfügbar machen, stellt einige eindeutige Herausforderung dar. Beispielsweise tritt ein potenzielles Problem beim separaten Anwendung derselben COM-Assembly verweisen. Dies ist üblich, wenn eine neue Version einer Assembly installiert ist und von einer anderen Anwendung ist immer noch die alte Version der Assembly. Wenn Sie eine Assembly, die gemeinsam eine DLL deinstallieren, können Sie versehentlich es nicht verfügbar an anderen Assemblys vornehmen.  
  
 Um dieses Problem zu vermeiden, sollten Sie freigegebene Assemblys zum globalen Assemblycache (GAC) installieren und verwenden ein Mergemodul für die Komponente. Wenn Sie die Anwendung im GAC installieren können, sollten sie in einem versionsspezifischen Unterverzeichnis des CommonFilesFolder installiert.  
  
 Assemblys, die nicht gemeinsam genutzt werden, sollten im Verzeichnis mit der aufrufenden Anwendung nebeneinander befinden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Globaler Assemblycache](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)

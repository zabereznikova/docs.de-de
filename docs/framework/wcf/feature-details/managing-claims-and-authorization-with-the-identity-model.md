---
title: Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell
description: Erfahren Sie mehr über die wichtigsten Programmier Konzepte für das WCF-Identitäts Modell, ein Anspruchs basiertes Modell zum Durchführen der Autorisierung.
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- WCF security
- claims [WCF], managing with the Identity Model
- claims [WCF]
- authorization [WCF], managing with the Identity Model
ms.assetid: 099defbb-5d35-434e-9336-1a49b9ec7663
ms.openlocfilehash: 0d5687f8ac5021c008254f0f5cc453eda5e538c7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245127"
---
# <a name="managing-claims-and-authorization-with-the-identity-model"></a>Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell
Mit Autorisierung wird der Prozess bezeichnet, in dem entschieden wird, welche Entitäten berechtigt sind, eine Computerressource zu ändern, anzuzeigen oder anderweitig darauf zuzugreifen. In einem Unternehmen sind beispielsweise nur Manager berechtigt, auf die Dateien ihrer Mitarbeiter zuzugreifen. Windows Communication Foundation (WCF) unterstützt zwei Mechanismen zum Durchführen der Autorisierungs Verarbeitung. Der erste Mechanismus ermöglicht Ihnen, die Autorisierung mit vorhandenen CLR-Konstrukten (Common Language Runtime) zu kontrollieren. Die zweite ist ein Anspruchs basiertes Modell, das als *Identitäts Modell*bezeichnet wird. WCF verwendet das Identitäts Modell zum Erstellen von Ansprüchen aus eingehenden Nachrichten. Identitäts Modellklassen können erweitert werden, um neue Anspruchs Typen für benutzerdefinierte Autorisierungs Schemas zu unterstützen. Dieses Thema bietet eine Übersicht über die wichtigsten Programmierkonzepte der Identitätsmodellfunktion sowie eine Auflistung der wichtigsten von dieser Funktion verwendeten Klassen.  
  
## <a name="identity-model-scenarios"></a>Identitätsmodellszenarien  
 Die folgenden Szenarien stellen die Verwendung des Identitätsmodells dar.  
  
### <a name="scenario-1-supporting-identity-role-and-group-claims"></a>Szenario 1: Unterstützung der Ansprüche Identität, Rolle und Gruppe  
 Benutzer senden Nachrichten an einen Webdienst. Für die Anforderungen der Zugriffssteuerung des Webdiensts werden Identität, Rollen und Gruppen verwendet. Der Absender der Nachricht wird einer Reihe von Rollen oder Gruppen zugeordnet. Mit Rollen- oder Gruppeninformationen werden Zugriffsprüfungen ausgeführt.  
  
### <a name="scenario-2-supporting-rich-claims"></a>Szenario 2: Unterstützung umfangreicher Ansprüche  
 Benutzer senden Nachrichten an einen Webdienst. Für die Anforderungen der Zugriffssteuerung des Webdiensts ist ein umfangreicheres Modell als Identität, Rollen oder Gruppen erforderlich. Der Webdienst bestimmt anhand des umfangreichen anspruchsbasierten Modells, ob ein bestimmter Benutzer Zugriff auf eine bestimmte geschützte Ressource hat. Ein Benutzer kann beispielsweise berechtigt sein, bestimmte Informationen, wie Gehaltsinformationen, zu lesen, während andere Benutzer keinen Zugriff auf diese Informationen haben.  
  
### <a name="scenario-3-mapping-disparate-claims"></a>Szenario 3: Zuordnen von ungleichartigen Ansprüchen  
 Ein Benutzer sendet eine Nachricht an einen Webdienst. Der Benutzer kann seine Benutzerinformationen auf verschiedene Weisen angeben: X.509-Zertifikat, Benutzernamentoken oder Kerberos-Token. Der Webdienst muss unabhängig vom Typ der Benutzeranmeldeinformationen die gleichen Zugriffsteuerungsprüfungen durchführen. Werden im Laufe der Zeit zusätzliche Anmeldeinformationstypen unterstützt, sollte das System entsprechend weiterentwickelt werden.  
  
### <a name="scenario-4-determining-access-to-multiple-resources"></a>Szenario 4: Bestimmen des Zugriffs auf mehrere Ressourcen  
 Ein Webdienst versucht, auf mehrere Ressourcen zuzugreifen. Der Webdienst bestimmt, auf welche geschützten Ressourcen ein bestimmter Benutzer Zugriff hat, indem die mit dem Benutzer verbundenen Ansprüche mit den Ansprüchen verglichen werden, die für den Zugriff auf die Ressource erforderlich sind.  
  
## <a name="identity-model-terms"></a>Begriffe im Zusammenhang mit dem Identitätsmodell  
 Die folgende Liste definiert Schlüsselbegriffe, die Identitätsmodellkonzepte beschreiben.  
  
 Autorisierungsrichtlinie  
 Eine Reihe von Regeln für die Zuordnung eines Satzes von Eingabeansprüchen zu einem Satz von Ausgabeansprüchen. Die Auswertung der Autorisierungsrichtlinie führt dazu, dass Sätze von Ansprüchen zu einem Evaluierungskontext und schließlich zu einem Autorisierungskontext hinzugefügt werden.  
  
 Autorisierungskontext  
 Eine Gruppe von Anspruchssätzen und 0 (null) oder mehr Eigenschaften. Das Ergebnis der Auswertung von einer oder mehreren Autorisierungsrichtlinien.  
  
 Anspruch  
 Eine Kombination aus Anspruchstyp, Recht und Wert.  
  
 Satz von Ansprüchen  
 Ein Satz von Ansprüchen, die von einem bestimmten Aussteller ausgegeben werden.  
  
 Anspruchstyp  
 Eine Art Anspruch. Ansprüche, die von der Identitätsmodell-API definiert werden, sind Eigenschaften der <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>-Klasse. Beispiele für vom System bereitgestellte Anspruchstypen sind <xref:System.IdentityModel.Claims.ClaimTypes.Dns%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Email%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Hash%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Rsa%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Sid%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Spn%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.System%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Thumbprint%2A>, <xref:System.IdentityModel.Claims.ClaimTypes.Uri%2A> und <xref:System.IdentityModel.Claims.ClaimTypes.X500DistinguishedName%2A>.  
  
 Evaluierungskontext  
 Ein Kontext, in dem eine Autorisierungsrichtlinie ausgewertet wird. Er enthält Eigenschaften und Anspruchssätze. Der Evaluierungskontext wird zur Grundlage eines Autorisierungskontexts, sobald die Auswertung abgeschlossen ist.  
  
 Identitätsanspruch  
 Ein Anspruch, dessen Berechtigung die Identität ist.  
  
 Aussteller  
 Ein Anspruchssatz, der mindestens einen Identitätsanspruch enthält und von dem angenommen wird, dass er einen anderen Anspruchssatz ausgestellt hat.  
  
 Eigenschaften  
 Eine Reihe von Informationen, die mit einem Evaluierungskontext oder einem Autorisierungskontext verbunden sind.  
  
 Geschützte Ressource  
 Ein Element im System, dessen Verwendung, Zugriff oder anderweitige Bearbeitung nur erfolgen kann, wenn bestimmte Anforderungen erfüllt sind.  
  
 Rechts  
 Eine Berechtigung für eine Ressource. Rechte, die von der Identitätsmodell-API definiert werden, sind Eigenschaften der <xref:System.IdentityModel.Claims.Rights>-Klasse. Beispiele für vom System bereitgestellte Rechte sind <xref:System.IdentityModel.Claims.Rights.Identity%2A> und <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.  
  
 Wert  
 Ein Element, für das ein Recht beansprucht wird.  
  
## <a name="claims"></a>Ansprüche  
 Das Identitätsmodell ist ein anspruchsbasiertes System. Ansprüche beschreiben die Funktionen, die mit einer Entität im System, häufig einem Benutzer des entsprechenden Systems, verbunden sind. Den mit einer bestimmten Entität verbundenen Satz von Ansprüchen kann man sich als Schlüssel vorstellen. Die jeweiligen Ansprüche definieren die Form des Schlüssels, ähnlich wie bei einem richtigen Schlüssel, der zum Öffnen einer Tür verwendet wird. Ansprüche dienen dazu, Zugriff auf Ressourcen zu erhalten. Der Zugriff auf eine bestimmte geschützte Ressource wird bestimmt, indem die für den Zugriff auf diese Ressource erforderlichen Ansprüche mit den Ansprüchen verglichen werden, die mit der Entität verbunden sind, die zuzugreifen versucht.  
  
 Ein Anspruch ist der Ausdruck eines Rechts in Bezug auf einen bestimmten Wert. Ein Recht kann beispielsweise "Lesen", "Schreiben" oder "Ausführen" sein. Ein Wert kann eine Datenbank, eine Datei, ein Postfach oder eine Eigenschaft sein. Ansprüche besitzen außerdem einen Anspruchtyp. Die Kombination aus Anspruchstyp und Recht stellt den Mechanismus zur Angabe der Funktionen in Bezug auf den Wert dar. Ein Anspruch des Typs "file" mit der rechten "Read"-Berechtigung über den Wert "Biography.doc" gibt beispielsweise an, dass die Entität, mit der ein solcher Anspruch verknüpft ist, über Lesezugriff auf die Datei Biography.doc verfügt. Ein Anspruch des Typs "Name" mit der rechten "PossessProperty" für den Wert "Martin" gibt an, dass die Entität, mit der ein solcher Anspruch verknüpft ist, eine Namenseigenschaft mit dem Wert "Martin" besitzt.  
  
 Obwohl verschiedene Anspruchstypen und Rechte im Rahmen des Identitätsmodells definiert werden, ist das System erweiterbar und ermöglicht verschiedenen Systemen, die auf die Identitätsmodellinfrastruktur aufsetzen, bei Bedarf zusätzliche Anspruchstypen und Rechte zu definieren.  
  
### <a name="identity-claims"></a>Identitätsansprüche  
 Ein besonderes Recht stellt die Identität dar. Ansprüche, die dieses Recht besitzen, sagen etwas über die Identität der Entität aus. Ein Anspruch des Typs "Benutzer Prinzipal Name" (UPN) mit dem Wert " someone@example.com " und dem Recht der Identität gibt z. b. eine bestimmte Identität in einer bestimmten Domäne an.  
  
#### <a name="system-identity-claim"></a>Systemidentitätsanspruch  
 Das Identitätsmodell definiert einen Identitätsanspruch: System. Der Identitätsanspruch "System" gibt an, dass eine Entität der aktuellen Anwendung oder dem aktuellen System entspricht.  
  
### <a name="sets-of-claims"></a>Sätze von Ansprüchen  
 Das Modell von Ansprüchen, die die Identität darstellen, ist wichtig, da Ansprüche immer von einer Entität im System ausgegeben werden, auch wenn diese Entität letztendlich eine Form eines "Selbst" ist. Ansprüche werden in Gruppen zusammengefasst, die als Sätze bezeichnet werden. Jeder Satz hat einen Aussteller. Ein Aussteller ist lediglich ein Satz von Ansprüchen. Eine solche rekursive Beziehung muss schließlich enden, und jeder Anspruchssatz kann sein eigener Aussteller sein.  
  
 Die folgende Abbildung zeigt ein Beispiel mit drei Sätzen von Ansprüchen, wobei ein Satz von Ansprüchen als eigener Aussteller einen Satz von Ansprüchen besitzt, der wiederum den Anspruchssatz "System" als Aussteller aufweist. Daher bilden Sätze von Ansprüchen eine Hierarchie mit einer willkürlichen Tiefe.  
  
 ![Sätze von Ansprüchen innerhalb der Hierarchie.](./media/managing-claims-and-authorization-with-the-identity-model/claims-sets-hierarchy.gif)  
  
 Mehrere Sätze von Ansprüchen können denselben ausstellenden Anspruchssatz aufweisen, wie in der folgenden Abbildung dargestellt:
  
 ![Mehrere Sätze von Ansprüchen mit dem gleichen ausstellenden Anspruchssatz.](./media/managing-claims-and-authorization-with-the-identity-model/multiple-claim-sets-same-issuing-claim-set.gif)  
  
 Mit Ausnahme eines Anspruchssatzes, der sein eigener Aussteller ist, bietet das Identitätsmodell keine Unterstützung für Anspruchssätze zur Bildung einer Schleife. Daher kann es nie zu einer Situation kommen, in der der Anspruchssatz A vom Anspruchssatz B ausgestellt wird, der wiederum selbst von Anspruchsatz A ausgestellt wurde. Außerdem bietet das Identitätsmodell keine Unterstützung für Anspruchssätze mit mehreren Ausstellern. Wenn zwei oder mehr Aussteller einen bestimmten Satz von Ansprüchen ausstellen müssen, müssen Sie mehrere Anspruchssätze verwenden. Jeder Satz enthält dabei dieselben Ansprüche, jedoch unterschiedliche Aussteller.  
  
### <a name="the-origin-of-claims"></a>Der Ursprung von Ansprüchen  
 Ansprüche können aus einer Vielzahl von Quellen stammen. Eine gängige Quelle für Ansprüche sind Anmeldeinformationen, die von einem Benutzer angegeben werden, z. B. als Teil einer an den Webdienst gesendeten Nachricht. Das System überprüft derartige Ansprüche, und diese Ansprüche werden Teil eines Satzes von mit dem Benutzer verbundenen Ansprüchen. Andere Systemkomponenten können ebenfalls die Quelle für Ansprüche sein, einschließlich, aber nicht beschränkt auf das Betriebssystem, den Netzwerkstapel, die Laufzeitumgebung oder die Anwendung. Darüber hinaus können auch Remotedienste eine Quelle für Ansprüche sein.  
  
### <a name="authorization-policies"></a>Autorisierungsrichtlinien  
 Im Identitätsmodell werden Ansprüche im Rahmen des Prozesses zur Evaluierung der Autorisierungsrichtlinie generiert. Eine Autorisierungsrichtlinie untersucht den (möglicherweise leeren) Satz von vorhandenen Ansprüchen und kann weitere Ansprüche basierend auf den bereits vorhandenen Ansprüchen und zusätzlich verfügbare Informationen hinzufügen. Dies schafft die Basis für die Zuordnung von Ansprüchen. Das Vorhandensein oder Fehlen von Ansprüchen im System beeinflusst das Verhalten einer Autorisierungsrichtlinie im Hinblick darauf, ob zusätzliche Ansprüche hinzugefügt werden.  
  
 Die Autorisierungsrichtlinie hat beispielsweise Zugriff auf eine Datenbank, die die Geburtstage der verschiedenen Entitäten, die das System verwenden, enthält. Die Autorisierungsrichtlinie verwendet diese Informationen, um einen "Over18"-Anspruch zum Kontext hinzuzufügen. Beachten Sie, dass dieser "Over18"-Anspruch keine anderen Informationen über die Entität offenlegt als die Tatsache, dass sie über 18 Jahre alt ist. Die Interpretation des "Over18"-Anspruchs hängt vom Verständnis der semantischen Bedeutung dieses Anspruchs ab. Die Autorisierungsrichtlinie, die den Anspruch hinzugefügt hat, versteht diese semantische Bedeutung bis zu einem gewissen Grad. Der Code, der daraufhin die Ansprüche untersucht, die sich aus der Richtlinienauswertung ergeben, erhält ebenfalls Informationen über diese semantische Bedeutung.  
  
 Für eine bestimmte Autorisierungsrichtlinie kann eine mehrfache Evaluierung erforderlich sein, da diese Autorisierungsrichtlinie während des Hinzufügens von Ansprüchen durch andere Autorisierungsrichtlinien noch weitere Ansprüche hinzufügen kann. Das Identitätsmodell wurde entwickelt, um die Evaluierung fortzusetzen, bis keine weiteren Ansprüche mehr von einer der gültigen Autorisierungsrichtlinien zum Kontext hinzugefügt werden. Diese fortlaufende Evaluierung der Autorisierungsrichtlinien verhindert, dass die Anforderung eine bestimmte Evaluierungsreihenfolge im Hinblick auf die Autorisierungsrichtlinien durchsetzt. Sie können in jeder beliebigen Reihenfolge evaluiert werden. Wenn beispielsweise die Richtlinie X nur den Anspruch Z hinzufügt, wenn die Richtlinie A den Anspruch B hinzugefügt hat, und wenn die Richtlinie X dann zuerst evaluiert wird, wird der Anspruch Z zunächst nicht hinzugefügt. Anschließend wird die Richtlinie A evaluiert, und diese fügt den Anspruch B hinzu. Die Richtlinie X wird dann ein zweites Mal evaluiert, und dieses Mal fügt sie den Anspruch Z hinzu.  
  
 Ein vorhandenes System kann mehrere gültige Autorisierungsrichtlinien besitzen.  
  
### <a name="a-key-making-machine"></a>Eine Schlüsselprägemaschine  
 Die Evaluierung einer Gruppe von verbundenen Autorisierungsrichtlinien ist mit dem Einsatz einer Maschine vergleichbar, die Schlüssel prägt. Die Autorisierungsrichtlinien werden jeweils evaluiert und Sätze von Ansprüchen generiert. So wird die Form des Schlüssels erzeugt. Nachdem die Form des Schlüssels fertig ist, kann er für das Öffnen von Schlössern verwendet werden. Die Form des Schlüssels wird in einem "Autorisierungskontext" gespeichert, der von einem Autorisierungs-Manager erstellt wird.  
  
### <a name="authorization-context"></a>Autorisierungskontext  
 Ein Autorisierungs-Manager evaluiert die verschiedenen Autorisierungsrichtlinien, wie beschrieben, und das Ergebnis ist ein Autorisierungskontext (ein Satz von Anspruchssätzen und einige zugehörige Eigenschaften). Der Autorisierungskontext kann untersucht werden, um zu bestimmen, welche Ansprüche in diesem Kontext vorhanden sind, welche Beziehungen zwischen den verschiedenen Ansprüchen bestehen (z. B. der ausstellende Anspruchssatz), und um sie schließlich mit einigen Anforderungen zu vergleichen, die sie für den Zugriff auf eine Ressource erfüllen müssen.  
  
### <a name="locks"></a>Locks  
 Wenn ein Autorisierungskontext (ein Satz von Ansprüchen) ein Schlüssel ist, dann bilden die Anforderungen, die zur Erteilung des Zugriffs auf eine bestimmte geschützte Ressource erfüllt werden müssen, das Schloss, in das der Schlüssel passen muss. Das Identitätsmodell legt nicht fest, wie diese Anforderungen ausgedrückt werden. Es beinhaltet jedoch angesichts der anspruchsbasierten Beschaffenheit des Systems den Vergleich der Ansprüche im Autorisierungskontext mit einem Satz von erforderlichen Ansprüchen.  
  
### <a name="a-recap"></a>Zusammenfassung  
 Das Identitätsmodell basiert auf dem Konzept von Ansprüchen. Ansprüche werden zu Sätzen zusammengefasst und in einem Autorisierungskontext aggregiert. Ein Autorisierungskontext enthält einen Satz von Ansprüchen und ist das Ergebnis der Evaluierung von einer oder mehreren Autorisierungsrichtlinien, die mit einem Autorisierungs-Manager verbunden sind. Anhand dieser Ansprüche kann bestimmt werden, ob die Zugriffsanforderungen erfüllt werden. In der folgenden Abbildung ist die Beziehung zwischen verschiedenen Identitätsmodellkonzepten dargestellt.  
  
 ![Verwalten von Ansprüchen und Autorisierung](media/xsi-recap.gif "xsi_recap")  
  
## <a name="wcf-and-identity-model"></a>WCF und Identitätsmodell  
 WCF verwendet die Identitäts Modell Infrastruktur als Grundlage für die Durchführung der Autorisierung. In WCF können Sie mithilfe der- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Klasse *Autorisierungs* Richtlinien als Teil eines Dienstanbieter angeben. Solche Autorisierungs Richtlinien werden als *externe Autorisierungs Richtlinien*bezeichnet und können die Anspruchs Verarbeitung basierend auf der lokalen Richtlinie oder durch Interaktion mit einem Remote Dienst durchführen. Der Autorisierungs-Manager, der durch die-Klasse dargestellt wird, <xref:System.ServiceModel.ServiceAuthorizationManager> wertet externe Autorisierungs Richtlinien zusammen mit Autorisierungs Richtlinien aus, die die verschiedenen Anmelde Informationstypen (Token) erkennen, und füllt den sogenannten *Autorisierungs Kontext* mit den Ansprüchen für eine eingehende Nachricht. Der Autorisierungskontext wird durch die <xref:System.IdentityModel.Policy.AuthorizationContext>-Klasse dargestellt.  
  
## <a name="identity-model-programming"></a>Programmierung des Identitätsmodells  
 In der folgenden Tabelle wird das Objektmodell beschrieben, mit dem Identitätsmodellerweiterungen programmiert werden. Diese Klassen sind alle entweder im <xref:System.IdentityModel.Policy>-Namespace oder im <xref:System.IdentityModel.Claims>-Namespace enthalten.  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|Autorisierungskomponente|Eine Identitätsmodellklasse, die die <xref:System.IdentityModel.Policy.IAuthorizationComponent>-Schnittstelle implementiert.|  
|<xref:System.IdentityModel.Policy.IAuthorizationComponent>|Eine Schnittstelle, die eine einzelne schreibgeschützte Zeichen folgen Eigenschaft bereitstellt: ID. Der Wert dieser Eigenschaft ist für jede Instanz im System, die diese Schnittstelle implementiert, eindeutig.|  
|<xref:System.IdentityModel.Policy.AuthorizationContext>|Eine *Autorisierungs Komponente* , die einen Satz von- `ClaimSet` Instanzen mit 0 (null) oder mehr Eigenschaften enthält; das Ergebnis der Auswertung einer oder mehrerer Autorisierungs Richtlinien.|  
|<xref:System.IdentityModel.Claims.Claim>|Eine Kombination aus Anspruchstyp, Recht und Wert. Die Bestandteile Recht und Wert werden durch den Anspruchstyp beschränkt.|  
|<xref:System.IdentityModel.Claims.ClaimSet>|Eine abstrakte Basisklasse. Eine Auflistung von `Claim`-Instanzen.|  
|<xref:System.IdentityModel.Claims.DefaultClaimSet>|Eine versiegelte Klasse. Eine Implementierung der `ClaimSet`-Klasse.|  
|<xref:System.IdentityModel.Policy.EvaluationContext>|Eine abstrakte Basisklasse. Wird bei der Richtlinienevaluierung an eine Autorisierungsrichtlinie weitergegeben.|  
|<xref:System.IdentityModel.Policy.IAuthorizationPolicy>|Eine von abgeleitete `IAuthorizationComponent` und von Autorisierungs Richtlinien Klassen implementierte Schnittstelle.|  
|<xref:System.IdentityModel.Claims.Rights>|Eine statische Klasse, die vordefinierte "Recht"-Werte enthält.|  
  
 Die folgenden Klassen werden ebenfalls für die Programmierung des Identitätsmodells verwendet, sind jedoch nicht im <xref:System.IdentityModel.Policy>-Namespace oder im <xref:System.IdentityModel.Claims>-Namespace vorhanden.  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|<xref:System.ServiceModel.ServiceAuthorizationManager>|Eine Klasse, die eine Methode – <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> – zur Durchführung von anspruchsbasierten Autorisierungsprüfungen für jeden Vorgang in einem Dienst bereitstellt. Sie müssen von der Klasse ableiten und die Methode überschreiben.|  
|<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>|Eine versiegelte Klasse, die verschiedene Eigenschaften in Bezug auf das Verhalten eines Diensts bietet, da sie zur Autorisierung gehört.|  
|<xref:System.ServiceModel.ServiceSecurityContext>|Eine Klasse, die den Sicherheitskontext, einschließlich Autorisierungskontext, für den aktuell ausgeführten (oder auszuführenden) Vorgang bereitstellt. Eine Instanz dieser Klasse ist Teil des <xref:System.ServiceModel.OperationContext>.|  
  
### <a name="significant-members"></a>Wesentliche Member  
 Die folgenden Member werden im Allgemeinen zum Erstellen neuer Anspruchstypen verwendet.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>|Abgeleitete Klassen implementieren diese Methode zur Durchführung von anspruchsbasierten Zugriffsprüfungen, bevor Vorgänge in einem Dienst ausgeführt werden. Alle Informationen im bereitgestellten <xref:System.ServiceModel.OperationContext> oder anderswo können untersucht werden, wenn die Zugriffsprüfungsentscheidung getroffen wird. Wenn <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>`true` zurückgibt, wird der Zugriff erteilt und der Vorgang darf ausgeführt werden. Gibt `CheckAccessCore``false` zurück, wird der Zugriff verweigert und der Vorgang wird nicht ausgeführt. Ein Beispiel finden Sie unter Gewusst [wie: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).|  
|<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>|Gibt den <xref:System.ServiceModel.ServiceAuthorizationManager> für den Dienst zurück. Der <xref:System.ServiceModel.ServiceAuthorizationManager> ist für Autorisierungsentscheidungen verantwortlich.|  
|<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>|Die Sammlung benutzerdefinierter Autorisierungsrichtlinien, die für den Dienst angegeben sind. Diese Richtlinien werden zusätzlich zu den Richtlinien evaluiert, die mit den Anmeldeinformationen in eingehenden Nachrichten verbunden sind.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Policy.EvaluationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationComponent>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims>
- <xref:System.IdentityModel.Policy>
- <xref:System.IdentityModel.Tokens>
- <xref:System.IdentityModel.Selectors>
- [Ansprüche und Token](claims-and-tokens.md)
- [Ansprüche und das Verweigern des Zugriffs auf Ressourcen](claims-and-denying-access-to-resources.md)
- [Erstellen von Ansprüchen und Ressourcenwerte](claim-creation-and-resource-values.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs](../extending/how-to-create-a-custom-claim.md)
- [Vorgehensweise: Vergleichen von Ansprüchen](../extending/how-to-compare-claims.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Autorisierungsrichtlinie](../extending/how-to-create-a-custom-authorization-policy.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Sicherheitsübersicht](security-overview.md)
- [Autorisierung](authorization-in-wcf.md)

---
title: "Empfohlene Vorgehensweisen: Versionsverwaltung von Datenverträgen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data contracts
- service contracts
- best practices [WCF], data contract versioning
- Windows Communication Foundation, data contracts
ms.assetid: bf0ab338-4d36-4e12-8002-8ebfdeb346cb
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78373d482aaaa0121a6c2708f543188d9cc9464d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-data-contract-versioning"></a>Empfohlene Vorgehensweisen: Versionsverwaltung von Datenverträgen
In diesem Thema sind die empfohlenen Vorgehensweisen zum Erstellen von Datenverträgen aufgeführt, die sich im Laufe der Zeit auf einfache Weise entwickeln können. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Datenverträgen finden Sie in die Themen in [mithilfe von Datenverträgen](../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
## <a name="note-on-schema-validation"></a>Hinweis zur Schemavalidierung  
 Beim Beschreiben der Versionsverwaltung von Datenverträgen ist es wichtig zu wissen, dass das von [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] exportierte Datenvertragsschema nicht über Unterstützung für die Versionsverwaltung verfügt. Die Elemente sind standardmäßig lediglich als optional gekennzeichnet.  
  
 Dies bedeutet, dass sogar ein sehr häufig verwendetes Versionsverwaltungsszenario, beispielsweise das Hinzufügen eines neuen Datenmembers, nicht nahtlos für ein bestimmtes Schema implementiert werden kann. Die neueren Versionen eines Datenvertrags (beispielsweise mit einem neuen Datenmember) können bei Verwendung des alten Schemas nicht überprüft werden.  
  
 Es gibt jedoch viele Szenarios, bei denen die strenge Schemakompatibilität nicht erforderlich ist. Viele Webdienstplattformen, zum Beispiel auch [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] und die mithilfe von ASP.NET erstellten XML-Webdienste, führen die Schemavalidierung standardmäßig nicht durch. Aus diesem Grund tolerieren sie zusätzliche Elemente, die vom Schema nicht beschrieben werden. Wenn Sie mit Plattformen dieser Art arbeiten, sind viele Versionsverwaltungsszenarios einfacher zu implementieren.  
  
 Es gibt also zwei Sätze von Richtlinien für die Versionsverwaltung von Datenverträgen: Einen Satz für Szenarios, bei denen die genaue Schemagültigkeit wichtig ist, und einen Satz für Szenarios, bei denen dies nicht wichtig ist.  
  
## <a name="versioning-when-schema-validation-is-required"></a>Versionsverwaltung, wenn eine Schemavalidierung erforderlich ist  
 Wenn die genaue Schemagültigkeit in allen Richtungen erforderlich ist (neu in alt und alt in neu), sollten Datenverträge als unveränderlich angesehen werden. Wenn die Versionsverwaltung erforderlich ist, sollte ein neuer Datenvertrag mit einem anderen Namen oder Namespace erstellt werden, und der Dienstvertrag, der den Datentyp nutzt, muss eine entsprechende Version erhalten.  
  
 Angenommen, Sie verwenden einen Dienstvertrag für die Bestellungsverarbeitung mit dem Namen `PoProcessing` mit einem `PostPurchaseOrder`-Vorgang, der einen Parameter erfordert, der einem `PurchaseOrder`-Datenvertrag entspricht. Wenn der `PurchaseOrder`-Vertrag geändert werden muss, müssen Sie einen neuen Datenvertrag erstellen (also `PurchaseOrder2`), der die Änderungen enthält. Sie müssen die Versionsverwaltung dann auf Dienstvertragsebene behandeln. Beispiele: Sie erstellen einen `PostPurchaseOrder2`-Vorgang, der den `PurchaseOrder2`-Parameter verwendet, oder Sie erstellen einen `PoProcessing2`-Dienstvertrag, bei dem der `PostPurchaseOrder`-Vorgang einen `PurchaseOrder2`-Datenvertrag verwendet.  
  
 Beachten Sie, dass Änderungen von Datenverträgen, auf die von anderen Datenverträgen verwiesen wird, auch für die Dienstmodellebene gelten. Angenommen, der `PurchaseOrder`-Datenvertrag aus dem vorherigen Szenario muss nicht geändert werden. Er enthält jedoch einen Datenmember eines `Customer`-Datenvertrags, der wiederum einen Datenmember des `Address`-Datenvertrags enthält, der allerdings geändert werden muss. In diesem Fall müssen Sie einen `Address2`-Datenvertrag mit den erforderlichen Änderungen, einen `Customer2`-Datenvertrag, der den `Address2`-Datenmember enthält, und einen `PurchaseOrder2`-Datenvertrag erstellen, der einen `Customer2`-Datenmember enthält. Wie im vorherigen Fall muss der Dienstvertrag ebenfalls über eine Versionsangabe verfügen.  
  
 Obwohl in diesen Beispielen Namen geändert werden (indem eine "2" angefügt wird), ist es empfehlenswert, anstelle von Namen Namespaces zu ändern, indem neue Namespaces mit einer Versionsnummer oder einem Datum angefügt werden. Der `http://schemas.contoso.com/2005/05/21/PurchaseOrder`-Datenvertrag würde beispielsweise eine Änderung des `http://schemas.contoso.com/2005/10/14/PurchaseOrder`-Datenvertrags bewirken.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]Bewährte Methoden: [Dienstversionsverwaltung](../../../docs/framework/wcf/service-versioning.md).  
  
 In einigen Fällen müssen Sie die genaue Einhaltung für Nachrichten sicherstellen, die von Ihrer Anwendung gesendet werden, können sich jedoch nicht darauf verlassen, dass die eingehenden Nachrichten die Vorgaben des Schemas genau einhalten. In diesem Fall besteht die Gefahr, dass eine eingehende Nachricht fremde Daten enthält. Die fremden Werte werden gespeichert und von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] zurückgegeben, wodurch sich Fehlermeldungen mit dem Hinweis auf ungültige Schemas ergeben. Um dieses Problem zu vermeiden, sollten Sie die Roundtripfunktion deaktivieren. Hierfür gibt es zwei Möglichkeiten.  
  
-   Implementieren Sie die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle für keinen der Typen.  
  
-   Wenden Sie ein <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut auf Ihren Dienstvertrag an, und legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A>-Eigenschaft dabei auf `true` fest.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Round-Tripping, finden Sie unter [aufwärtskompatible Datenverträge](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
## <a name="versioning-when-schema-validation-is-not-required"></a>Versionsverwaltung, wenn eine Schemavalidierung nicht erforderlich ist  
 Die genaue Schemakompatibilität ist nur selten erforderlich. Viele Plattformen tolerieren zusätzliche Elemente, die von einem Schema nicht beschrieben werden. Solange diese toleriert wird, der vollständige Satz von Funktionen in der beschriebenen [Datenvertragsversionsverwaltung](../../../docs/framework/wcf/feature-details/data-contract-versioning.md) und [aufwärtskompatible Datenverträge](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md) kann verwendet werden. Die folgenden Richtlinien sind zu empfehlen.  
  
 Einige Richtlinien müssen exakt befolgt werden, um neue Versionen eines Typs zu senden zu können, wenn ein älterer Typ erwartet wird, bzw. um einen älteren Typ senden zu können, wenn ein neuer Typ erwartet wird. Andere Richtlinien sind nicht unbedingt erforderlich, hier jedoch aufgeführt, da sich die zukünftige Versionsverwaltung von Schemas darauf auswirken kann.  
  
1.  Versuchen Sie nicht, Datenverträge mit einer Versionsangabe zu versehen, indem Sie die Typvererbung verwenden. Um höhere Versionen zu erstellen, ändern Sie entweder den Datenvertrag für einen vorhandenen Typ oder erstellen einen neuen nicht verwandten Typ.  
  
2.  Die Verwendung der Vererbung im Zusammenhang mit Datenverträgen ist zulässig, vorausgesetzt, die Vererbung wird nicht als Mechanismus für die Versionsverwaltung verwendet und bestimmte Regeln werden befolgt. Wenn ein Typ von einem bestimmten Basistyp abgeleitet ist, sollten Sie diese Ableitung in einer zukünftigen Version nicht in einen anderen Basistyp ändern (es sei denn, dieser verfügt über denselben Datenvertrag). Dabei gilt eine Ausnahme: Sie können einen Typ in die Hierarchie zwischen einem Datenvertragstyp und seinem Basistyp einfügen, jedoch nur dann, wenn dieser keine Datenmember mit demselben Namen wie andere Member in beliebigen Versionen der anderen Typen der Hierarchie enthält. Im Allgemeinen kann die Verwendung von Datenmembern mit demselben Namen auf verschiedenen Ebenen einer Vererbungshierarchie zu ernsthaften Problemen bei der Versionsverwaltung führen. Dies sollte daher vermieden werden.  
  
3.  Implementieren Sie immer das <xref:System.Runtime.Serialization.IExtensibleDataObject>, indem Sie mit der ersten Version eines Datenvertrags beginnen, um Roundtrips zu aktivieren. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Aufwärtskompatible Datenverträge](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md). Wenn Sie eine oder mehrere Versionen eines Typs veröffentlicht haben, ohne diese Schnittstelle zu implementieren, sollten Sie sie in der nächsten Version des Typs implementieren.  
  
4.  Ändern Sie den Datenvertragsnamen oder den Namespace in höheren Versionen nicht. Wenn Sie den Namen oder Namespace des Typs ändern, der dem Datenvertrag zugrunde liegt, müssen Sie darauf achten, den Datenvertragsnamen und Namespace beizubehalten, indem Sie die entsprechenden Mechanismen verwenden, zum Beispiel die <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>-Eigenschaft des <xref:System.Runtime.Serialization.DataContractAttribute>. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Benennung, finden Sie unter [Datenvertragsnamen](../../../docs/framework/wcf/feature-details/data-contract-names.md).  
  
5.  Nehmen Sie in höheren Versionen keine Änderungen an den Namen von Datenmembern vor. Wenn Sie den Namen des Felds, der Eigenschaft oder des Ereignisses ändern, das bzw. die dem Datenmember zugrunde liegt, können Sie die `Name`-Eigenschaft des <xref:System.Runtime.Serialization.DataMemberAttribute> verwenden, um den vorhandenen Datenmembernamen beizubehalten.  
  
6.  Nehmen Sie in höheren Versionen keine Änderungen am Typ eines Felds, einer Eigenschaft oder eines einem Datenmember zugrunde liegenden Ereignisses vor, die sich dahingehend auswirken, dass sich der resultierende Datenvertrag für diesen Datenmember ändert. Denken Sie daran, dass Schnittstellentypen mit <xref:System.Object> äquivalent sind, um den erwarteten Datenvertrag ermitteln zu können.  
  
7.  Nehmen Sie in höheren Versionen keine Änderung der Reihenfolge der vorhandenen Datenmember vor, indem Sie die <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>-Eigenschaft des <xref:System.Runtime.Serialization.DataMemberAttribute>-Attributs anpassen.  
  
8.  In höheren Versionen können neue Datenmember hinzugefügt werden. Sie sollten dabei immer die folgenden Regeln einhalten:  
  
    1.  Die <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>-Eigenschaft muss immer auf ihrem Standardwert `false` belassen werden.  
  
    2.  Wenn der Standardwert `null` bzw. "0" für den Member nicht akzeptabel ist, muss mithilfe von <xref:System.Runtime.Serialization.OnDeserializingAttribute> eine Rückrufmethode bereitgestellt werden, um einen geeigneten Standardwert anzugeben, falls der Member im eingehenden Stream nicht enthalten ist. [!INCLUDE[crabout](../../../includes/crabout-md.md)]der Rückruf finden Sie unter [versionstolerante Serialisierungsrückrufe](../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md).  
  
    3.  Sie sollten die `Order`-Eigenschaft des `DataMemberAttribute` verwenden, um sicherzustellen, dass alle neu hinzugefügten Datenmember nach den vorhandenen Datenmembern stehen. Die empfohlene Vorgehensweise lautet wie folgt: Für keinen Datenmember der ersten Version eines Datenvertrags sollte die `Order`-Eigenschaft festgelegt sein. Sie sollten für alle Datenmember, die Sie in Version 2 des Datenvertrags hinzugefügt haben, die `Order`-Eigenschaft auf "2" festlegen. Ebenso sollten Sie die `Order`-Eigenschaft für in Version 3 des Datenvertrags hinzugefügte Datenmember auf "3" festlegen usw. Es ist zulässig, mehrere Datenmember auf die gleiche `Order`-Nummer festzulegen.  
  
9. Entfernen Sie Datenmember in höheren Versionen auch dann nicht, wenn die <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>-Eigenschaft in den vorherigen Versionen auf der Standardeinstellung `false` belassen wurde.  
  
10. Ändern Sie die `IsRequired`-Eigenschaft für vorhandene Datenmember nicht von Version zu Version.  
  
11. Ändern Sie die `IsRequired`-Eigenschaft für erforderliche Datenmember (wobei `true` den Wert `EmitDefaultValue` hat) nicht von Version zu Version.  
  
12. Versuchen Sie nicht, verzweigte Versionsverwaltungshierarchien zu erstellen. Es sollte also immer ein Pfad in mindestens einer Richtung zwischen Versionen vorhanden sein, indem nur die von diesen Richtlinien zugelassenen Änderungen verwendet werden.  
  
     Wenn zum Beispiel die Version 1 eines Person-Datenvertrags nur den Name-Datenmember enthält, sollten Sie keine Version 2a des Vertrags erstellen, indem Sie nur den Age-Member hinzufügen, und keine Version 2b, indem Sie nur den Address-Member hinzufügen. Der Übergang von 2a zu 2b würde das Entfernen von "Age" und das Hinzufügen von "Address" umfassen. Ein Übergang in der anderen Richtung würde hingegen das Entfernen von "Address" und das Hinzufügen von "Age" umfassen. Das Entfernen von Membern ist im Rahmen dieser Richtlinien nicht zulässig.  
  
13. Sie sollten generell keine neuen Untertypen vorhandener Datenvertragstypen in einer neuen Version Ihrer Anwendung erstellen. Außerdem sollten Sie keine neuen Datenverträge erstellen, die anstelle von Datenmembern verwendet werden, die als Objekt oder als Schnittstellentypen deklariert sind. Das Erstellen dieser neuen Klassen ist nur zulässig, wenn Sie wissen, dass Sie die neuen Typen der Liste der bekannten Typen aller Instanzen der alten Anwendung hinzufügen können. Es kann zum Beispiel sein, dass Sie in Version 1 Ihrer Anwendung den LibraryItem-Datenvertragstyp mit den Datenvertrags-Untertypen "Buch" und "Zeitung" verwenden. "LibraryItem" würde dann über eine Liste der bekannten Typen verfügen, die "Buch" und "Zeitung" enthält. Angenommen, Sie fügen in Version 2 den Typ "Zeitschrift" hinzu, bei dem es sich um einen Untertyp von "LibraryItem" handelt. Wenn Sie eine Zeitschrift-Instanz von Version&#160;2 an Version&#160;1 senden, ist der Zeitschrift-Datenvertrag nicht in der Liste der bekannten Typen enthalten, und es wird eine Ausnahme ausgelöst.  
  
14. Sie sollten zwischen Versionen keine Enumerationsmember hinzufügen oder entfernen. Außerdem sollten Sie Enumerationsmember nicht umbenennen, es sei denn, Sie verwenden die Name-Eigenschaft des `EnumMemberAttribute`-Attributs, um ihre Namen im Datenvertragsmodell identisch zu halten.  
  
15. Sammlungen sind austauschbar im datenvertragsmodell wie beschrieben in [Sammlungstypen in Datenverträgen](../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md). Dies ermöglicht einen hohen Grad an Flexibilität. Sie sollten jedoch sicherstellen, dass Sie einen Auflistungstyp von Version zu Version nicht versehentlich auf nicht austauschbare Weise ändern. Wechseln Sie zum Beispiel nicht von einer nicht anpassbaren Auflistung (also ohne `CollectionDataContractAttribute`-Attribut) zu einer anpassbaren Auflistung oder umgekehrt. Ändern Sie auch nicht die Eigenschaften für das `CollectionDataContractAttribute` von Version zu Version. Die einzige zulässige Änderung ist das Hinzufügen einer Name- oder Namespace-Eigenschaft, wenn sich der Name oder Namespace des zugrunde liegenden Auflistungstyps geändert hat und Sie Name und Namespace des Datenvertrags an den Stand der vorherigen Version anpassen müssen.  
  
 Einige der Richtlinien, die hier aufgelistet sind, können problemlos ignoriert werden, wenn besondere Umstände gelten. Stellen Sie sicher, dass Sie den Mechanismus der Serialisierung, Deserialisierung und Schemaverwendung vollständig verstanden haben, bevor Sie von den Richtlinien abweichen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>  
 <xref:System.Runtime.Serialization.ExtensionDataObject>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 [Verwenden von Datenverträgen](../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Datenvertrags-Versionsverwaltung](../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [Datenvertragsnamen](../../../docs/framework/wcf/feature-details/data-contract-names.md)  
 [Aufwärtskompatible Datenverträge](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)  
 [Versionstolerante Serialisierungsrückrufe](../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)

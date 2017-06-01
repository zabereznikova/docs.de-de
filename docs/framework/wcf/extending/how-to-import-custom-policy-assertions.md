---
title: "Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen
Richtlinienassertionen beschreiben die Funktionen und Anforderungen eines Dienstendpunkts.  Clientanwendungen können Richtlinienassertionen in Dienstmetadaten nutzen, um die Clientbindung zu konfigurieren oder den Dienstvertrag für einen Dienstendpunkt anzupassen.  
  
 Benutzerdefinierte Richtlinienassertionen werden importiert, durch die Implementierung der <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> -Schnittstelle und das Objekt übergeben, in das Metadatensystem oder durch die Registrierung der Implementierungstyps Geben Sie in der Anwendungskonfigurationsdatei.  Die Implementierung von der <xref:System.ServiceModel.Description.IPolicyImportExtension> Schnittstelle muss einen Standardkonstruktor bereitstellen.  
  
### <a name="to-import-custom-policy-assertions"></a>So importieren Sie benutzerdefinierte Richtlinienassertionen  
  
1.  Implementieren der <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> Schnittstelle für eine Klasse. Anweisungen hierzu finden Sie in den folgenden Verfahren.  
  
2.  Fügen Sie das benutzerdefinierte Richtlinienimportprogramm durch eines der folgenden Verfahren ein:  
  
3.  Verwenden einer Konfigurationsdatei. Anweisungen hierzu finden Sie in den folgenden Verfahren.  
  
4.  Mithilfe einer Konfigurationsdatei mit [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Anweisungen hierzu finden Sie in den folgenden Verfahren.  
  
5.  Programmgesteuertes Einfügen des Richtlinienimportprogramms. Anweisungen hierzu finden Sie in den folgenden Verfahren.  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a>So implementieren Sie die System.ServiceModel.Description.IPolicyImportExtension-Schnittstelle auf einer beliebigen Klasse  
  
1.  In der <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=fullName> -Methode für jedes richtliniensubjekt, die Sie interessieren, finden Sie die Richtlinienassertionen, die zu importierenden durch Aufrufen der geeigneten Methode (je nach dem Umfang der Assertion, die gewünschten) auf den <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=fullName> Objekt an die Methode übergeben. Im folgenden Codebeispiel wird veranschaulicht, wie Sie die <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=fullName> Methode, um die benutzerdefinierte Assertion ausfindig, und entfernen es aus der Auflistung in einem Schritt. Wenn Sie die Entfernen-Methode verwenden, um die Assertion ausfindig zu machen und zu entfernen, müssen Sie Schritt 4 nicht durchführen.  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2.  Verarbeiten Sie die Richtlinienassertionen. Beachten Sie, dass das Richtliniensystem keine geschachtelten Richtlinien und `wsp:optional` normalisiert. Sie müssen diese Konstrukte in der Richtlinienimport-Erweiterungsimplementierung verarbeiten.  
  
3.  Nehmen Sie die Anpassung an der Bindung oder am Vertrag vor, die bzw. der die von der Richtlinienassertion festgelegte Funktion oder Anforderung erfüllt. In der Regel geben Assertionen an, dass eine Bindung eine besondere Konfiguration oder ein bestimmtes Bindungselement erfordert. Nehmen Sie diese Änderungen durch den Zugriff auf die <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=fullName> Eigenschaft. Andere Assertionen erfordern, dass Sie den Vertrag ändern.  Sie können Zugriff auf und Ändern der Vertrag mit dem <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=fullName> Eigenschaft.  Beachten Sie, dass Ihr Richtlinienimportprogramm möglicherweise mehrere Male für dieselbe Bindung und für denselben Vertrag, aber für unterschiedliche Richtlinienalternativen aufgerufen wird, wenn der Import einer Richtlinienalternative fehlschlägt. Der Code sollte diesem Verhalten gegenüber flexibel sein.  
  
4.  Entfernen Sie die die benutzerdefinierte Richtlinienassertion aus der Assertionsauflistung. Wenn Sie die Assertion nicht entfernen, geht [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] davon aus, dass der Richtlinienimport nicht erfolgreich war und importiert die zugeordnete Bindung nicht. Wenn Sie verwendet die <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=fullName> Methode, um die benutzerdefinierte Assertion ausfindig, und entfernt sie aus der Auflistung in einem Schritt, Sie nicht diesen Schritt ausführen müssen.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a>So fügen Sie das benutzerdefinierte Richtlinienimportprogramm mit einer Konfigurationsdatei ins Metadatensystem ein  
  
1.  Typ des Importprogramms zum Hinzufügen der `<extensions>` Element innerhalb der [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) Element in der Clientkonfigurationsdatei.  
  
     <!-- TODO: review snippet reference [!code[CustomPolicySample#7](../../../../samples/snippets/common/VS_Snippets_CFX/custompolicysample/common/client.exe.config#7)]  -->
     <!-- TODO: review snippet reference [!code-csharp[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]  -->
     <!-- TODO: review snippet reference [!code-vb[CustomPolicySample#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.exe.config#7)]  -->  
  
2.  Verwenden Sie in der Clientanwendung die <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName> oder <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName> zum Auflösen der Metadaten das Importprogramm wird daraufhin automatisch ausgelöst.  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a>So fügen Sie das benutzerdefinierte Richtlinienimportprogramm mithilfe der Datei Svcutil.exe ins Metadatensystem ein  
  
1.  Typ des Importprogramms zum Hinzufügen der `<extensions>` Element innerhalb der [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) Element in der Datei "svcutil.exe.config". Über die Option `/svcutilConfig` können Sie Svcutil.exe darüber hinaus dazu bringen, Typen von Richtlinienprogrammen zu laden, die in einer anderen Konfigurationsdatei gespeichert sind.  
  
2.  Verwendung [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Importieren von Metadaten und das Importprogramm werden automatisch aufgerufen.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a>So fügen Sie das benutzerdefinierte Richtlinienimportprogramm programmgesteuert ins Metadatensystem ein  
  
1.  Fügen Sie den Importer, um die <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=fullName> Eigenschaft (z. B. bei Verwendung der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>) vor dem Import der Metadaten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName>   
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>   
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName>   
 [Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)
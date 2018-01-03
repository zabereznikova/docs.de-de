---
title: OLE DB-Schemaauflistungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e120ea532b6da455e31ce7345b6c4b2be1ec975f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="44874-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="44874-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="44874-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="44874-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="44874-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="44874-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="44874-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="44874-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="44874-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="44874-106">Tables</span></span>  
  
-   <span data-ttu-id="44874-107">Columns</span><span class="sxs-lookup"><span data-stu-id="44874-107">Columns</span></span>  
  
-   <span data-ttu-id="44874-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="44874-108">Procedures</span></span>  
  
-   <span data-ttu-id="44874-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="44874-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="44874-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="44874-110">Catalog</span></span>  
  
-   <span data-ttu-id="44874-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="44874-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="44874-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="44874-112">Tables</span></span>  
  
|<span data-ttu-id="44874-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-113">ColumnName</span></span>|<span data-ttu-id="44874-114">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-115">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-116">String</span></span>|  
|<span data-ttu-id="44874-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-118">String</span></span>|  
|<span data-ttu-id="44874-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-119">TABLE_NAME</span></span>|<span data-ttu-id="44874-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-120">String</span></span>|  
|<span data-ttu-id="44874-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-121">TABLE_TYPE</span></span>|<span data-ttu-id="44874-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-122">String</span></span>|  
|<span data-ttu-id="44874-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-123">TABLE_GUID</span></span>|<span data-ttu-id="44874-124">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-124">Guid</span></span>|  
|<span data-ttu-id="44874-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-125">DESCRIPTION</span></span>|<span data-ttu-id="44874-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-126">String</span></span>|  
|<span data-ttu-id="44874-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-127">TABLE_PROPID</span></span>|<span data-ttu-id="44874-128">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-128">Int64</span></span>|  
|<span data-ttu-id="44874-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-129">DATE_CREATED</span></span>|<span data-ttu-id="44874-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-130">DateTime</span></span>|  
|<span data-ttu-id="44874-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-131">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="44874-133">Columns</span><span class="sxs-lookup"><span data-stu-id="44874-133">Columns</span></span>  
  
|<span data-ttu-id="44874-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-134">ColumnName</span></span>|<span data-ttu-id="44874-135">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-136">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-137">String</span></span>|  
|<span data-ttu-id="44874-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-139">String</span></span>|  
|<span data-ttu-id="44874-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-140">TABLE_NAME</span></span>|<span data-ttu-id="44874-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-141">String</span></span>|  
|<span data-ttu-id="44874-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-142">COLUMN_NAME</span></span>|<span data-ttu-id="44874-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-143">String</span></span>|  
|<span data-ttu-id="44874-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-144">COLUMN_GUID</span></span>|<span data-ttu-id="44874-145">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-145">Guid</span></span>|  
|<span data-ttu-id="44874-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-146">COLUMN_PROPID</span></span>|<span data-ttu-id="44874-147">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-147">Int64</span></span>|  
|<span data-ttu-id="44874-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-149">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-149">Int64</span></span>|  
|<span data-ttu-id="44874-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="44874-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-151">Boolean</span></span>|  
|<span data-ttu-id="44874-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="44874-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-153">String</span></span>|  
|<span data-ttu-id="44874-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="44874-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="44874-155">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-155">Int64</span></span>|  
|<span data-ttu-id="44874-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="44874-156">IS_NULLABLE</span></span>|<span data-ttu-id="44874-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-157">Boolean</span></span>|  
|<span data-ttu-id="44874-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-158">DATA_TYPE</span></span>|<span data-ttu-id="44874-159">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-159">Int32</span></span>|  
|<span data-ttu-id="44874-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-160">TYPE_GUID</span></span>|<span data-ttu-id="44874-161">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-161">Guid</span></span>|  
|<span data-ttu-id="44874-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="44874-163">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-163">Int64</span></span>|  
|<span data-ttu-id="44874-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="44874-165">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-165">Int64</span></span>|  
|<span data-ttu-id="44874-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="44874-167">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-167">Int32</span></span>|  
|<span data-ttu-id="44874-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="44874-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="44874-169">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-169">Int16</span></span>|  
|<span data-ttu-id="44874-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="44874-171">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-171">Int64</span></span>|  
|<span data-ttu-id="44874-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="44874-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-173">String</span></span>|  
|<span data-ttu-id="44874-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="44874-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-175">String</span></span>|  
|<span data-ttu-id="44874-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="44874-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-177">String</span></span>|  
|<span data-ttu-id="44874-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="44874-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-179">String</span></span>|  
|<span data-ttu-id="44874-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="44874-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-181">String</span></span>|  
|<span data-ttu-id="44874-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-182">COLLATION_NAME</span></span>|<span data-ttu-id="44874-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-183">String</span></span>|  
|<span data-ttu-id="44874-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="44874-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-185">String</span></span>|  
|<span data-ttu-id="44874-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="44874-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-187">String</span></span>|  
|<span data-ttu-id="44874-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-188">DOMAIN_NAME</span></span>|<span data-ttu-id="44874-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-189">String</span></span>|  
|<span data-ttu-id="44874-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-190">DESCRIPTION</span></span>|<span data-ttu-id="44874-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-191">String</span></span>|  
|<span data-ttu-id="44874-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="44874-192">COLUMN_LCID</span></span>|<span data-ttu-id="44874-193">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-193">Int32</span></span>|  
|<span data-ttu-id="44874-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="44874-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="44874-195">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-195">Int32</span></span>|  
|<span data-ttu-id="44874-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="44874-196">COLUMN_SORTID</span></span>|<span data-ttu-id="44874-197">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-197">Int32</span></span>|  
|<span data-ttu-id="44874-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="44874-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="44874-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="44874-199">Byte[]</span></span>|  
|<span data-ttu-id="44874-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="44874-200">IS_COMPUTED</span></span>|<span data-ttu-id="44874-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="44874-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="44874-202">Procedures</span></span>  
  
|<span data-ttu-id="44874-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-203">ColumnName</span></span>|<span data-ttu-id="44874-204">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="44874-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-206">String</span></span>|  
|<span data-ttu-id="44874-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="44874-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-208">String</span></span>|  
|<span data-ttu-id="44874-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="44874-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-210">String</span></span>|  
|<span data-ttu-id="44874-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="44874-212">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-212">Int16</span></span>|  
|<span data-ttu-id="44874-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="44874-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="44874-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-214">String</span></span>|  
|<span data-ttu-id="44874-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-215">DESCRIPTION</span></span>|<span data-ttu-id="44874-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-216">String</span></span>|  
|<span data-ttu-id="44874-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-217">DATE_CREATED</span></span>|<span data-ttu-id="44874-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-218">DateTime</span></span>|  
|<span data-ttu-id="44874-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-219">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="44874-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="44874-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="44874-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-222">ColumnName</span></span>|<span data-ttu-id="44874-223">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="44874-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-225">String</span></span>|  
|<span data-ttu-id="44874-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="44874-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-227">String</span></span>|  
|<span data-ttu-id="44874-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="44874-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-229">String</span></span>|  
|<span data-ttu-id="44874-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-230">PARAMETER_NAME</span></span>|<span data-ttu-id="44874-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-231">String</span></span>|  
|<span data-ttu-id="44874-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-233">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-233">Int32</span></span>|  
|<span data-ttu-id="44874-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="44874-235">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-235">Int32</span></span>|  
|<span data-ttu-id="44874-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="44874-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-237">Boolean</span></span>|  
|<span data-ttu-id="44874-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="44874-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-239">String</span></span>|  
|<span data-ttu-id="44874-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="44874-240">IS_NULLABLE</span></span>|<span data-ttu-id="44874-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-241">Boolean</span></span>|  
|<span data-ttu-id="44874-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-242">DATA_TYPE</span></span>|<span data-ttu-id="44874-243">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-243">Int32</span></span>|  
|<span data-ttu-id="44874-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="44874-245">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-245">Int64</span></span>|  
|<span data-ttu-id="44874-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="44874-247">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-247">Int64</span></span>|  
|<span data-ttu-id="44874-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="44874-249">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-249">Int32</span></span>|  
|<span data-ttu-id="44874-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="44874-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="44874-251">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-251">Int16</span></span>|  
|<span data-ttu-id="44874-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-252">DESCRIPTION</span></span>|<span data-ttu-id="44874-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-253">String</span></span>|  
|<span data-ttu-id="44874-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-254">TYPE_NAME</span></span>|<span data-ttu-id="44874-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-255">String</span></span>|  
|<span data-ttu-id="44874-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="44874-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="44874-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="44874-258">Catalog</span></span>  
  
|<span data-ttu-id="44874-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-259">ColumnName</span></span>|<span data-ttu-id="44874-260">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-261">CATALOG_NAME</span></span>|<span data-ttu-id="44874-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-262">String</span></span>|  
|<span data-ttu-id="44874-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-263">DESCRIPTION</span></span>|<span data-ttu-id="44874-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="44874-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="44874-265">Indexes</span></span>  
  
|<span data-ttu-id="44874-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-266">ColumnName</span></span>|<span data-ttu-id="44874-267">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-268">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-269">String</span></span>|  
|<span data-ttu-id="44874-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-271">String</span></span>|  
|<span data-ttu-id="44874-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-272">TABLE_NAME</span></span>|<span data-ttu-id="44874-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-273">String</span></span>|  
|<span data-ttu-id="44874-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-274">INDEX_CATALOG</span></span>|<span data-ttu-id="44874-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-275">String</span></span>|  
|<span data-ttu-id="44874-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="44874-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-277">String</span></span>|  
|<span data-ttu-id="44874-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-278">INDEX_NAME</span></span>|<span data-ttu-id="44874-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-279">String</span></span>|  
|<span data-ttu-id="44874-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="44874-280">PRIMARY_KEY</span></span>|<span data-ttu-id="44874-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-281">Boolean</span></span>|  
|<span data-ttu-id="44874-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="44874-282">UNIQUE</span></span>|<span data-ttu-id="44874-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-283">Boolean</span></span>|  
|<span data-ttu-id="44874-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="44874-284">CLUSTERED</span></span>|<span data-ttu-id="44874-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-285">Boolean</span></span>|  
|<span data-ttu-id="44874-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-286">TYPE</span></span>|<span data-ttu-id="44874-287">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-287">Int32</span></span>|  
|<span data-ttu-id="44874-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="44874-288">FILL_FACTOR</span></span>|<span data-ttu-id="44874-289">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-289">Int32</span></span>|  
|<span data-ttu-id="44874-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="44874-290">INITIAL_SIZE</span></span>|<span data-ttu-id="44874-291">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-291">Int32</span></span>|  
|<span data-ttu-id="44874-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="44874-292">NULLS</span></span>|<span data-ttu-id="44874-293">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-293">Int32</span></span>|  
|<span data-ttu-id="44874-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="44874-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="44874-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-295">Boolean</span></span>|  
|<span data-ttu-id="44874-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="44874-296">AUTO_UPDATE</span></span>|<span data-ttu-id="44874-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-297">Boolean</span></span>|  
|<span data-ttu-id="44874-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="44874-298">NULL_COLLATION</span></span>|<span data-ttu-id="44874-299">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-299">Int32</span></span>|  
|<span data-ttu-id="44874-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-301">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-301">Int64</span></span>|  
|<span data-ttu-id="44874-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-302">COLUMN_NAME</span></span>|<span data-ttu-id="44874-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-303">String</span></span>|  
|<span data-ttu-id="44874-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-304">COLUMN_GUID</span></span>|<span data-ttu-id="44874-305">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-305">Guid</span></span>|  
|<span data-ttu-id="44874-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-306">COLUMN_PROPID</span></span>|<span data-ttu-id="44874-307">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-307">Int64</span></span>|  
|<span data-ttu-id="44874-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="44874-308">COLLATION</span></span>|<span data-ttu-id="44874-309">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-309">Int16</span></span>|  
|<span data-ttu-id="44874-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="44874-310">CARDINALITY</span></span>|<span data-ttu-id="44874-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="44874-311">Decimal</span></span>|  
|<span data-ttu-id="44874-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="44874-312">PAGES</span></span>|<span data-ttu-id="44874-313">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-313">Int32</span></span>|  
|<span data-ttu-id="44874-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="44874-314">FILTER_CONDITION</span></span>|<span data-ttu-id="44874-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-315">String</span></span>|  
|<span data-ttu-id="44874-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="44874-316">INTEGRATED</span></span>|<span data-ttu-id="44874-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="44874-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="44874-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="44874-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="44874-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="44874-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="44874-320">Tables</span></span>  
  
-   <span data-ttu-id="44874-321">Columns</span><span class="sxs-lookup"><span data-stu-id="44874-321">Columns</span></span>  
  
-   <span data-ttu-id="44874-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="44874-322">Procedures</span></span>  
  
-   <span data-ttu-id="44874-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="44874-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="44874-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="44874-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="44874-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="44874-325">Views</span></span>  
  
-   <span data-ttu-id="44874-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="44874-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="44874-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="44874-327">Tables</span></span>  
  
|<span data-ttu-id="44874-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-328">ColumnName</span></span>|<span data-ttu-id="44874-329">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-330">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-331">String</span></span>|  
|<span data-ttu-id="44874-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-333">String</span></span>|  
|<span data-ttu-id="44874-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-334">TABLE_NAME</span></span>|<span data-ttu-id="44874-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-335">String</span></span>|  
|<span data-ttu-id="44874-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-336">TABLE_TYPE</span></span>|<span data-ttu-id="44874-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-337">String</span></span>|  
|<span data-ttu-id="44874-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-338">TABLE_GUID</span></span>|<span data-ttu-id="44874-339">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-339">Guid</span></span>|  
|<span data-ttu-id="44874-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-340">DESCRIPTION</span></span>|<span data-ttu-id="44874-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-341">String</span></span>|  
|<span data-ttu-id="44874-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-342">TABLE_PROPID</span></span>|<span data-ttu-id="44874-343">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-343">Int64</span></span>|  
|<span data-ttu-id="44874-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-344">DATE_CREATED</span></span>|<span data-ttu-id="44874-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-345">DateTime</span></span>|  
|<span data-ttu-id="44874-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-346">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="44874-348">Columns</span><span class="sxs-lookup"><span data-stu-id="44874-348">Columns</span></span>  
  
|<span data-ttu-id="44874-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-349">ColumnName</span></span>|<span data-ttu-id="44874-350">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-351">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-352">String</span></span>|  
|<span data-ttu-id="44874-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-354">String</span></span>|  
|<span data-ttu-id="44874-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-355">TABLE_NAME</span></span>|<span data-ttu-id="44874-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-356">String</span></span>|  
|<span data-ttu-id="44874-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-357">COLUMN_NAME</span></span>|<span data-ttu-id="44874-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-358">String</span></span>|  
|<span data-ttu-id="44874-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-359">COLUMN_GUID</span></span>|<span data-ttu-id="44874-360">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-360">Guid</span></span>|  
|<span data-ttu-id="44874-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-361">COLUMN_PROPID</span></span>|<span data-ttu-id="44874-362">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-362">Int64</span></span>|  
|<span data-ttu-id="44874-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-364">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-364">Int64</span></span>|  
|<span data-ttu-id="44874-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="44874-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-366">Boolean</span></span>|  
|<span data-ttu-id="44874-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="44874-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-368">String</span></span>|  
|<span data-ttu-id="44874-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="44874-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="44874-370">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-370">Int64</span></span>|  
|<span data-ttu-id="44874-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="44874-371">IS_NULLABLE</span></span>|<span data-ttu-id="44874-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-372">Boolean</span></span>|  
|<span data-ttu-id="44874-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-373">DATA_TYPE</span></span>|<span data-ttu-id="44874-374">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-374">Int32</span></span>|  
|<span data-ttu-id="44874-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-375">TYPE_GUID</span></span>|<span data-ttu-id="44874-376">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-376">Guid</span></span>|  
|<span data-ttu-id="44874-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="44874-378">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-378">Int64</span></span>|  
|<span data-ttu-id="44874-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="44874-380">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-380">Int64</span></span>|  
|<span data-ttu-id="44874-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="44874-382">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-382">Int32</span></span>|  
|<span data-ttu-id="44874-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="44874-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="44874-384">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-384">Int16</span></span>|  
|<span data-ttu-id="44874-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="44874-386">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-386">Int64</span></span>|  
|<span data-ttu-id="44874-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="44874-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-388">String</span></span>|  
|<span data-ttu-id="44874-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="44874-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-390">String</span></span>|  
|<span data-ttu-id="44874-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="44874-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-392">String</span></span>|  
|<span data-ttu-id="44874-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="44874-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-394">String</span></span>|  
|<span data-ttu-id="44874-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="44874-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-396">String</span></span>|  
|<span data-ttu-id="44874-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-397">COLLATION_NAME</span></span>|<span data-ttu-id="44874-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-398">String</span></span>|  
|<span data-ttu-id="44874-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="44874-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-400">String</span></span>|  
|<span data-ttu-id="44874-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="44874-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-402">String</span></span>|  
|<span data-ttu-id="44874-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-403">DOMAIN_NAME</span></span>|<span data-ttu-id="44874-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-404">String</span></span>|  
|<span data-ttu-id="44874-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-405">DESCRIPTION</span></span>|<span data-ttu-id="44874-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="44874-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="44874-407">Procedures</span></span>  
  
|<span data-ttu-id="44874-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-408">ColumnName</span></span>|<span data-ttu-id="44874-409">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="44874-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-411">String</span></span>|  
|<span data-ttu-id="44874-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="44874-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-413">String</span></span>|  
|<span data-ttu-id="44874-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="44874-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-415">String</span></span>|  
|<span data-ttu-id="44874-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="44874-417">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-417">Int16</span></span>|  
|<span data-ttu-id="44874-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="44874-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="44874-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-419">String</span></span>|  
|<span data-ttu-id="44874-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-420">DESCRIPTION</span></span>|<span data-ttu-id="44874-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-421">String</span></span>|  
|<span data-ttu-id="44874-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-422">DATE_CREATED</span></span>|<span data-ttu-id="44874-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-423">DateTime</span></span>|  
|<span data-ttu-id="44874-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-424">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="44874-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="44874-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="44874-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-427">ColumnName</span></span>|<span data-ttu-id="44874-428">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="44874-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-430">String</span></span>|  
|<span data-ttu-id="44874-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="44874-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-432">String</span></span>|  
|<span data-ttu-id="44874-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="44874-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-434">String</span></span>|  
|<span data-ttu-id="44874-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-435">COLUMN_NAME</span></span>|<span data-ttu-id="44874-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-436">String</span></span>|  
|<span data-ttu-id="44874-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-437">COLUMN_GUID</span></span>|<span data-ttu-id="44874-438">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-438">Guid</span></span>|  
|<span data-ttu-id="44874-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-439">COLUMN_PROPID</span></span>|<span data-ttu-id="44874-440">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-440">Int64</span></span>|  
|<span data-ttu-id="44874-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="44874-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="44874-442">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-442">Int64</span></span>|  
|<span data-ttu-id="44874-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-444">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-444">Int64</span></span>|  
|<span data-ttu-id="44874-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="44874-445">IS_NULLABLE</span></span>|<span data-ttu-id="44874-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-446">Boolean</span></span>|  
|<span data-ttu-id="44874-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-447">DATA_TYPE</span></span>|<span data-ttu-id="44874-448">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-448">Int32</span></span>|  
|<span data-ttu-id="44874-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-449">TYPE_GUID</span></span>|<span data-ttu-id="44874-450">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-450">Guid</span></span>|  
|<span data-ttu-id="44874-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="44874-452">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-452">Int64</span></span>|  
|<span data-ttu-id="44874-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="44874-454">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-454">Int64</span></span>|  
|<span data-ttu-id="44874-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="44874-456">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-456">Int32</span></span>|  
|<span data-ttu-id="44874-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="44874-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="44874-458">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-458">Int16</span></span>|  
|<span data-ttu-id="44874-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-459">DESCRIPTION</span></span>|<span data-ttu-id="44874-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-460">String</span></span>|  
|<span data-ttu-id="44874-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="44874-461">OVERLOAD</span></span>|<span data-ttu-id="44874-462">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="44874-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="44874-463">Views</span></span>  
  
|<span data-ttu-id="44874-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-464">ColumnName</span></span>|<span data-ttu-id="44874-465">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-466">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-467">String</span></span>|  
|<span data-ttu-id="44874-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-469">String</span></span>|  
|<span data-ttu-id="44874-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-470">TABLE_NAME</span></span>|<span data-ttu-id="44874-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-471">String</span></span>|  
|<span data-ttu-id="44874-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="44874-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="44874-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-473">String</span></span>|  
|<span data-ttu-id="44874-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="44874-474">CHECK_OPTION</span></span>|<span data-ttu-id="44874-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-475">Boolean</span></span>|  
|<span data-ttu-id="44874-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="44874-476">IS_UPDATABLE</span></span>|<span data-ttu-id="44874-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-477">Boolean</span></span>|  
|<span data-ttu-id="44874-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-478">DESCRIPTION</span></span>|<span data-ttu-id="44874-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-479">String</span></span>|  
|<span data-ttu-id="44874-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-480">DATE_CREATED</span></span>|<span data-ttu-id="44874-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-481">DateTime</span></span>|  
|<span data-ttu-id="44874-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-482">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="44874-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="44874-484">Indexes</span></span>  
  
|<span data-ttu-id="44874-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-485">ColumnName</span></span>|<span data-ttu-id="44874-486">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-487">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-488">String</span></span>|  
|<span data-ttu-id="44874-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-490">String</span></span>|  
|<span data-ttu-id="44874-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-491">TABLE_NAME</span></span>|<span data-ttu-id="44874-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-492">String</span></span>|  
|<span data-ttu-id="44874-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-493">INDEX_CATALOG</span></span>|<span data-ttu-id="44874-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-494">String</span></span>|  
|<span data-ttu-id="44874-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="44874-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-496">String</span></span>|  
|<span data-ttu-id="44874-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-497">INDEX_NAME</span></span>|<span data-ttu-id="44874-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-498">String</span></span>|  
|<span data-ttu-id="44874-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="44874-499">PRIMARY_KEY</span></span>|<span data-ttu-id="44874-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-500">Boolean</span></span>|  
|<span data-ttu-id="44874-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="44874-501">UNIQUE</span></span>|<span data-ttu-id="44874-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-502">Boolean</span></span>|  
|<span data-ttu-id="44874-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="44874-503">CLUSTERED</span></span>|<span data-ttu-id="44874-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-504">Boolean</span></span>|  
|<span data-ttu-id="44874-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-505">TYPE</span></span>|<span data-ttu-id="44874-506">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-506">Int32</span></span>|  
|<span data-ttu-id="44874-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="44874-507">FILL_FACTOR</span></span>|<span data-ttu-id="44874-508">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-508">Int32</span></span>|  
|<span data-ttu-id="44874-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="44874-509">INITIAL_SIZE</span></span>|<span data-ttu-id="44874-510">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-510">Int32</span></span>|  
|<span data-ttu-id="44874-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="44874-511">NULLS</span></span>|<span data-ttu-id="44874-512">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-512">Int32</span></span>|  
|<span data-ttu-id="44874-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="44874-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="44874-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-514">Boolean</span></span>|  
|<span data-ttu-id="44874-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="44874-515">AUTO_UPDATE</span></span>|<span data-ttu-id="44874-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-516">Boolean</span></span>|  
|<span data-ttu-id="44874-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="44874-517">NULL_COLLATION</span></span>|<span data-ttu-id="44874-518">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-518">Int32</span></span>|  
|<span data-ttu-id="44874-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-520">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-520">Int64</span></span>|  
|<span data-ttu-id="44874-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-521">COLUMN_NAME</span></span>|<span data-ttu-id="44874-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-522">String</span></span>|  
|<span data-ttu-id="44874-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-523">COLUMN_GUID</span></span>|<span data-ttu-id="44874-524">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-524">Guid</span></span>|  
|<span data-ttu-id="44874-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-525">COLUMN_PROPID</span></span>|<span data-ttu-id="44874-526">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-526">Int64</span></span>|  
|<span data-ttu-id="44874-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="44874-527">COLLATION</span></span>|<span data-ttu-id="44874-528">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-528">Int16</span></span>|  
|<span data-ttu-id="44874-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="44874-529">CARDINALITY</span></span>|<span data-ttu-id="44874-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="44874-530">Decimal</span></span>|  
|<span data-ttu-id="44874-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="44874-531">PAGES</span></span>|<span data-ttu-id="44874-532">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-532">Int32</span></span>|  
|<span data-ttu-id="44874-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="44874-533">FILTER_CONDITION</span></span>|<span data-ttu-id="44874-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-534">String</span></span>|  
|<span data-ttu-id="44874-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="44874-535">INTEGRATED</span></span>|<span data-ttu-id="44874-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="44874-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="44874-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="44874-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="44874-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="44874-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="44874-539">Tables</span></span>  
  
-   <span data-ttu-id="44874-540">Columns</span><span class="sxs-lookup"><span data-stu-id="44874-540">Columns</span></span>  
  
-   <span data-ttu-id="44874-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="44874-541">Procedures</span></span>  
  
-   <span data-ttu-id="44874-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="44874-542">Views</span></span>  
  
-   <span data-ttu-id="44874-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="44874-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="44874-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="44874-544">Tables</span></span>  
  
|<span data-ttu-id="44874-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-545">ColumnName</span></span>|<span data-ttu-id="44874-546">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-547">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-548">String</span></span>|  
|<span data-ttu-id="44874-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-550">String</span></span>|  
|<span data-ttu-id="44874-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-551">TABLE_NAME</span></span>|<span data-ttu-id="44874-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-552">String</span></span>|  
|<span data-ttu-id="44874-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-553">TABLE_TYPE</span></span>|<span data-ttu-id="44874-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-554">String</span></span>|  
|<span data-ttu-id="44874-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-555">TABLE_GUID</span></span>|<span data-ttu-id="44874-556">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-556">Guid</span></span>|  
|<span data-ttu-id="44874-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-557">DESCRIPTION</span></span>|<span data-ttu-id="44874-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-558">String</span></span>|  
|<span data-ttu-id="44874-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-559">TABLE_PROPID</span></span>|<span data-ttu-id="44874-560">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-560">Int64</span></span>|  
|<span data-ttu-id="44874-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-561">DATE_CREATED</span></span>|<span data-ttu-id="44874-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-562">DateTime</span></span>|  
|<span data-ttu-id="44874-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-563">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="44874-565">Columns</span><span class="sxs-lookup"><span data-stu-id="44874-565">Columns</span></span>  
  
|<span data-ttu-id="44874-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-566">ColumnName</span></span>|<span data-ttu-id="44874-567">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-568">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-569">String</span></span>|  
|<span data-ttu-id="44874-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-571">String</span></span>|  
|<span data-ttu-id="44874-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-572">TABLE_NAME</span></span>|<span data-ttu-id="44874-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-573">String</span></span>|  
|<span data-ttu-id="44874-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-574">COLUMN_NAME</span></span>|<span data-ttu-id="44874-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-575">String</span></span>|  
|<span data-ttu-id="44874-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-576">COLUMN_GUID</span></span>|<span data-ttu-id="44874-577">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-577">Guid</span></span>|  
|<span data-ttu-id="44874-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-578">COLUMN_PROPID</span></span>|<span data-ttu-id="44874-579">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-579">Int64</span></span>|  
|<span data-ttu-id="44874-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-581">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-581">Int64</span></span>|  
|<span data-ttu-id="44874-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="44874-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-583">Boolean</span></span>|  
|<span data-ttu-id="44874-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="44874-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="44874-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-585">String</span></span>|  
|<span data-ttu-id="44874-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="44874-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="44874-587">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-587">Int64</span></span>|  
|<span data-ttu-id="44874-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="44874-588">IS_NULLABLE</span></span>|<span data-ttu-id="44874-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-589">Boolean</span></span>|  
|<span data-ttu-id="44874-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-590">DATA_TYPE</span></span>|<span data-ttu-id="44874-591">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-591">Int32</span></span>|  
|<span data-ttu-id="44874-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-592">TYPE_GUID</span></span>|<span data-ttu-id="44874-593">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-593">Guid</span></span>|  
|<span data-ttu-id="44874-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="44874-595">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-595">Int64</span></span>|  
|<span data-ttu-id="44874-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="44874-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="44874-597">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-597">Int64</span></span>|  
|<span data-ttu-id="44874-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="44874-599">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-599">Int32</span></span>|  
|<span data-ttu-id="44874-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="44874-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="44874-601">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-601">Int16</span></span>|  
|<span data-ttu-id="44874-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="44874-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="44874-603">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-603">Int64</span></span>|  
|<span data-ttu-id="44874-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="44874-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-605">String</span></span>|  
|<span data-ttu-id="44874-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="44874-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-607">String</span></span>|  
|<span data-ttu-id="44874-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="44874-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-609">String</span></span>|  
|<span data-ttu-id="44874-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="44874-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-611">String</span></span>|  
|<span data-ttu-id="44874-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="44874-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-613">String</span></span>|  
|<span data-ttu-id="44874-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-614">COLLATION_NAME</span></span>|<span data-ttu-id="44874-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-615">String</span></span>|  
|<span data-ttu-id="44874-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="44874-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-617">String</span></span>|  
|<span data-ttu-id="44874-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="44874-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-619">String</span></span>|  
|<span data-ttu-id="44874-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-620">DOMAIN_NAME</span></span>|<span data-ttu-id="44874-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-621">String</span></span>|  
|<span data-ttu-id="44874-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-622">DESCRIPTION</span></span>|<span data-ttu-id="44874-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="44874-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="44874-624">Procedures</span></span>  
  
|<span data-ttu-id="44874-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-625">ColumnName</span></span>|<span data-ttu-id="44874-626">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="44874-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-628">String</span></span>|  
|<span data-ttu-id="44874-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="44874-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-630">String</span></span>|  
|<span data-ttu-id="44874-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="44874-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-632">String</span></span>|  
|<span data-ttu-id="44874-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="44874-634">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-634">Int16</span></span>|  
|<span data-ttu-id="44874-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="44874-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="44874-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-636">String</span></span>|  
|<span data-ttu-id="44874-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-637">DESCRIPTION</span></span>|<span data-ttu-id="44874-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-638">String</span></span>|  
|<span data-ttu-id="44874-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-639">DATE_CREATED</span></span>|<span data-ttu-id="44874-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-640">DateTime</span></span>|  
|<span data-ttu-id="44874-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-641">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="44874-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="44874-643">Views</span></span>  
  
|<span data-ttu-id="44874-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-644">ColumnName</span></span>|<span data-ttu-id="44874-645">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-646">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-647">String</span></span>|  
|<span data-ttu-id="44874-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-649">String</span></span>|  
|<span data-ttu-id="44874-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-650">TABLE_NAME</span></span>|<span data-ttu-id="44874-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-651">String</span></span>|  
|<span data-ttu-id="44874-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="44874-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="44874-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-653">String</span></span>|  
|<span data-ttu-id="44874-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="44874-654">CHECK_OPTION</span></span>|<span data-ttu-id="44874-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-655">Boolean</span></span>|  
|<span data-ttu-id="44874-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="44874-656">IS_UPDATABLE</span></span>|<span data-ttu-id="44874-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-657">Boolean</span></span>|  
|<span data-ttu-id="44874-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44874-658">DESCRIPTION</span></span>|<span data-ttu-id="44874-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-659">String</span></span>|  
|<span data-ttu-id="44874-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="44874-660">DATE_CREATED</span></span>|<span data-ttu-id="44874-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-661">DateTime</span></span>|  
|<span data-ttu-id="44874-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="44874-662">DATE_MODIFIED</span></span>|<span data-ttu-id="44874-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="44874-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="44874-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="44874-664">Indexes</span></span>  
  
|<span data-ttu-id="44874-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="44874-665">ColumnName</span></span>|<span data-ttu-id="44874-666">DataType</span><span class="sxs-lookup"><span data-stu-id="44874-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="44874-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-667">TABLE_CATALOG</span></span>|<span data-ttu-id="44874-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-668">String</span></span>|  
|<span data-ttu-id="44874-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="44874-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-670">String</span></span>|  
|<span data-ttu-id="44874-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-671">TABLE_NAME</span></span>|<span data-ttu-id="44874-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-672">String</span></span>|  
|<span data-ttu-id="44874-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="44874-673">INDEX_CATALOG</span></span>|<span data-ttu-id="44874-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-674">String</span></span>|  
|<span data-ttu-id="44874-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="44874-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="44874-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-676">String</span></span>|  
|<span data-ttu-id="44874-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-677">INDEX_NAME</span></span>|<span data-ttu-id="44874-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-678">String</span></span>|  
|<span data-ttu-id="44874-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="44874-679">PRIMARY_KEY</span></span>|<span data-ttu-id="44874-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-680">Boolean</span></span>|  
|<span data-ttu-id="44874-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="44874-681">UNIQUE</span></span>|<span data-ttu-id="44874-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-682">Boolean</span></span>|  
|<span data-ttu-id="44874-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="44874-683">CLUSTERED</span></span>|<span data-ttu-id="44874-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-684">Boolean</span></span>|  
|<span data-ttu-id="44874-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="44874-685">TYPE</span></span>|<span data-ttu-id="44874-686">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-686">Int32</span></span>|  
|<span data-ttu-id="44874-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="44874-687">FILL_FACTOR</span></span>|<span data-ttu-id="44874-688">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-688">Int32</span></span>|  
|<span data-ttu-id="44874-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="44874-689">INITIAL_SIZE</span></span>|<span data-ttu-id="44874-690">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-690">Int32</span></span>|  
|<span data-ttu-id="44874-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="44874-691">NULLS</span></span>|<span data-ttu-id="44874-692">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-692">Int32</span></span>|  
|<span data-ttu-id="44874-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="44874-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="44874-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-694">Boolean</span></span>|  
|<span data-ttu-id="44874-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="44874-695">AUTO_UPDATE</span></span>|<span data-ttu-id="44874-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="44874-696">Boolean</span></span>|  
|<span data-ttu-id="44874-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="44874-697">NULL_COLLATION</span></span>|<span data-ttu-id="44874-698">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-698">Int32</span></span>|  
|<span data-ttu-id="44874-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="44874-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="44874-700">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-700">Int64</span></span>|  
|<span data-ttu-id="44874-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="44874-701">COLUMN_NAME</span></span>|<span data-ttu-id="44874-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-702">String</span></span>|  
|<span data-ttu-id="44874-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="44874-703">COLUMN_GUID</span></span>|<span data-ttu-id="44874-704">Guid</span><span class="sxs-lookup"><span data-stu-id="44874-704">Guid</span></span>|  
|<span data-ttu-id="44874-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="44874-705">COLUMN_PROPID</span></span>|<span data-ttu-id="44874-706">Int64</span><span class="sxs-lookup"><span data-stu-id="44874-706">Int64</span></span>|  
|<span data-ttu-id="44874-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="44874-707">COLLATION</span></span>|<span data-ttu-id="44874-708">Int16</span><span class="sxs-lookup"><span data-stu-id="44874-708">Int16</span></span>|  
|<span data-ttu-id="44874-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="44874-709">CARDINALITY</span></span>|<span data-ttu-id="44874-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="44874-710">Decimal</span></span>|  
|<span data-ttu-id="44874-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="44874-711">PAGES</span></span>|<span data-ttu-id="44874-712">Int32</span><span class="sxs-lookup"><span data-stu-id="44874-712">Int32</span></span>|  
|<span data-ttu-id="44874-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="44874-713">FILTER_CONDITION</span></span>|<span data-ttu-id="44874-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="44874-714">String</span></span>|  
|<span data-ttu-id="44874-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="44874-715">INTEGRATED</span></span>|<span data-ttu-id="44874-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="44874-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44874-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44874-717">See Also</span></span>  
 [<span data-ttu-id="44874-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="44874-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

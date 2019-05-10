---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6c3441e86d4c5267418cf8002ba17d539c464d5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645895"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="068e2-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="068e2-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="068e2-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="068e2-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="068e2-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="068e2-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="068e2-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="068e2-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="068e2-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="068e2-106">Tables</span></span>  
  
- <span data-ttu-id="068e2-107">Spalten</span><span class="sxs-lookup"><span data-stu-id="068e2-107">Columns</span></span>  
  
- <span data-ttu-id="068e2-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="068e2-108">Procedures</span></span>  
  
- <span data-ttu-id="068e2-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="068e2-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="068e2-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="068e2-110">Catalog</span></span>  
  
- <span data-ttu-id="068e2-111">Indizes</span><span class="sxs-lookup"><span data-stu-id="068e2-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="068e2-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="068e2-112">Tables</span></span>  
  
|<span data-ttu-id="068e2-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-113">ColumnName</span></span>|<span data-ttu-id="068e2-114">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-115">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-116">String</span></span>|  
|<span data-ttu-id="068e2-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-118">String</span></span>|  
|<span data-ttu-id="068e2-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-119">TABLE_NAME</span></span>|<span data-ttu-id="068e2-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-120">String</span></span>|  
|<span data-ttu-id="068e2-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-121">TABLE_TYPE</span></span>|<span data-ttu-id="068e2-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-122">String</span></span>|  
|<span data-ttu-id="068e2-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-123">TABLE_GUID</span></span>|<span data-ttu-id="068e2-124">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-124">Guid</span></span>|  
|<span data-ttu-id="068e2-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-125">DESCRIPTION</span></span>|<span data-ttu-id="068e2-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-126">String</span></span>|  
|<span data-ttu-id="068e2-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-127">TABLE_PROPID</span></span>|<span data-ttu-id="068e2-128">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-128">Int64</span></span>|  
|<span data-ttu-id="068e2-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-129">DATE_CREATED</span></span>|<span data-ttu-id="068e2-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-130">DateTime</span></span>|  
|<span data-ttu-id="068e2-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-131">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="068e2-133">Spalten</span><span class="sxs-lookup"><span data-stu-id="068e2-133">Columns</span></span>  
  
|<span data-ttu-id="068e2-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-134">ColumnName</span></span>|<span data-ttu-id="068e2-135">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-136">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-137">String</span></span>|  
|<span data-ttu-id="068e2-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-139">String</span></span>|  
|<span data-ttu-id="068e2-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-140">TABLE_NAME</span></span>|<span data-ttu-id="068e2-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-141">String</span></span>|  
|<span data-ttu-id="068e2-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-142">COLUMN_NAME</span></span>|<span data-ttu-id="068e2-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-143">String</span></span>|  
|<span data-ttu-id="068e2-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-144">COLUMN_GUID</span></span>|<span data-ttu-id="068e2-145">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-145">Guid</span></span>|  
|<span data-ttu-id="068e2-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-146">COLUMN_PROPID</span></span>|<span data-ttu-id="068e2-147">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-147">Int64</span></span>|  
|<span data-ttu-id="068e2-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-149">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-149">Int64</span></span>|  
|<span data-ttu-id="068e2-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="068e2-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-151">Boolean</span></span>|  
|<span data-ttu-id="068e2-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="068e2-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-153">String</span></span>|  
|<span data-ttu-id="068e2-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="068e2-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="068e2-155">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-155">Int64</span></span>|  
|<span data-ttu-id="068e2-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="068e2-156">IS_NULLABLE</span></span>|<span data-ttu-id="068e2-157">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-157">Boolean</span></span>|  
|<span data-ttu-id="068e2-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-158">DATA_TYPE</span></span>|<span data-ttu-id="068e2-159">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-159">Int32</span></span>|  
|<span data-ttu-id="068e2-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-160">TYPE_GUID</span></span>|<span data-ttu-id="068e2-161">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-161">Guid</span></span>|  
|<span data-ttu-id="068e2-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="068e2-163">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-163">Int64</span></span>|  
|<span data-ttu-id="068e2-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="068e2-165">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-165">Int64</span></span>|  
|<span data-ttu-id="068e2-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="068e2-167">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-167">Int32</span></span>|  
|<span data-ttu-id="068e2-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="068e2-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="068e2-169">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-169">Int16</span></span>|  
|<span data-ttu-id="068e2-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="068e2-171">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-171">Int64</span></span>|  
|<span data-ttu-id="068e2-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="068e2-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-173">String</span></span>|  
|<span data-ttu-id="068e2-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="068e2-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-175">String</span></span>|  
|<span data-ttu-id="068e2-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="068e2-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-177">String</span></span>|  
|<span data-ttu-id="068e2-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="068e2-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-179">String</span></span>|  
|<span data-ttu-id="068e2-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="068e2-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-181">String</span></span>|  
|<span data-ttu-id="068e2-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-182">COLLATION_NAME</span></span>|<span data-ttu-id="068e2-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-183">String</span></span>|  
|<span data-ttu-id="068e2-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="068e2-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-185">String</span></span>|  
|<span data-ttu-id="068e2-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="068e2-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-187">String</span></span>|  
|<span data-ttu-id="068e2-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-188">DOMAIN_NAME</span></span>|<span data-ttu-id="068e2-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-189">String</span></span>|  
|<span data-ttu-id="068e2-190">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-190">DESCRIPTION</span></span>|<span data-ttu-id="068e2-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-191">String</span></span>|  
|<span data-ttu-id="068e2-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="068e2-192">COLUMN_LCID</span></span>|<span data-ttu-id="068e2-193">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-193">Int32</span></span>|  
|<span data-ttu-id="068e2-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="068e2-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="068e2-195">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-195">Int32</span></span>|  
|<span data-ttu-id="068e2-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="068e2-196">COLUMN_SORTID</span></span>|<span data-ttu-id="068e2-197">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-197">Int32</span></span>|  
|<span data-ttu-id="068e2-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="068e2-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="068e2-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="068e2-199">Byte[]</span></span>|  
|<span data-ttu-id="068e2-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="068e2-200">IS_COMPUTED</span></span>|<span data-ttu-id="068e2-201">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="068e2-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="068e2-202">Procedures</span></span>  
  
|<span data-ttu-id="068e2-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-203">ColumnName</span></span>|<span data-ttu-id="068e2-204">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="068e2-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-206">String</span></span>|  
|<span data-ttu-id="068e2-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="068e2-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-208">String</span></span>|  
|<span data-ttu-id="068e2-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="068e2-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-210">String</span></span>|  
|<span data-ttu-id="068e2-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="068e2-212">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-212">Int16</span></span>|  
|<span data-ttu-id="068e2-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="068e2-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="068e2-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-214">String</span></span>|  
|<span data-ttu-id="068e2-215">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-215">DESCRIPTION</span></span>|<span data-ttu-id="068e2-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-216">String</span></span>|  
|<span data-ttu-id="068e2-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-217">DATE_CREATED</span></span>|<span data-ttu-id="068e2-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-218">DateTime</span></span>|  
|<span data-ttu-id="068e2-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-219">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="068e2-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="068e2-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="068e2-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-222">ColumnName</span></span>|<span data-ttu-id="068e2-223">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="068e2-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-225">String</span></span>|  
|<span data-ttu-id="068e2-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="068e2-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-227">String</span></span>|  
|<span data-ttu-id="068e2-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="068e2-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-229">String</span></span>|  
|<span data-ttu-id="068e2-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-230">PARAMETER_NAME</span></span>|<span data-ttu-id="068e2-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-231">String</span></span>|  
|<span data-ttu-id="068e2-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-233">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-233">Int32</span></span>|  
|<span data-ttu-id="068e2-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="068e2-235">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-235">Int32</span></span>|  
|<span data-ttu-id="068e2-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="068e2-237">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-237">Boolean</span></span>|  
|<span data-ttu-id="068e2-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="068e2-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-239">String</span></span>|  
|<span data-ttu-id="068e2-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="068e2-240">IS_NULLABLE</span></span>|<span data-ttu-id="068e2-241">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-241">Boolean</span></span>|  
|<span data-ttu-id="068e2-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-242">DATA_TYPE</span></span>|<span data-ttu-id="068e2-243">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-243">Int32</span></span>|  
|<span data-ttu-id="068e2-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="068e2-245">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-245">Int64</span></span>|  
|<span data-ttu-id="068e2-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="068e2-247">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-247">Int64</span></span>|  
|<span data-ttu-id="068e2-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="068e2-249">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-249">Int32</span></span>|  
|<span data-ttu-id="068e2-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="068e2-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="068e2-251">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-251">Int16</span></span>|  
|<span data-ttu-id="068e2-252">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-252">DESCRIPTION</span></span>|<span data-ttu-id="068e2-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-253">String</span></span>|  
|<span data-ttu-id="068e2-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-254">TYPE_NAME</span></span>|<span data-ttu-id="068e2-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-255">String</span></span>|  
|<span data-ttu-id="068e2-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="068e2-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="068e2-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="068e2-258">Catalog</span></span>  
  
|<span data-ttu-id="068e2-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-259">ColumnName</span></span>|<span data-ttu-id="068e2-260">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-261">CATALOG_NAME</span></span>|<span data-ttu-id="068e2-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-262">String</span></span>|  
|<span data-ttu-id="068e2-263">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-263">DESCRIPTION</span></span>|<span data-ttu-id="068e2-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="068e2-265">Indizes</span><span class="sxs-lookup"><span data-stu-id="068e2-265">Indexes</span></span>  
  
|<span data-ttu-id="068e2-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-266">ColumnName</span></span>|<span data-ttu-id="068e2-267">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-268">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-269">String</span></span>|  
|<span data-ttu-id="068e2-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-271">String</span></span>|  
|<span data-ttu-id="068e2-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-272">TABLE_NAME</span></span>|<span data-ttu-id="068e2-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-273">String</span></span>|  
|<span data-ttu-id="068e2-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-274">INDEX_CATALOG</span></span>|<span data-ttu-id="068e2-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-275">String</span></span>|  
|<span data-ttu-id="068e2-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="068e2-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-277">String</span></span>|  
|<span data-ttu-id="068e2-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-278">INDEX_NAME</span></span>|<span data-ttu-id="068e2-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-279">String</span></span>|  
|<span data-ttu-id="068e2-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="068e2-280">PRIMARY_KEY</span></span>|<span data-ttu-id="068e2-281">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-281">Boolean</span></span>|  
|<span data-ttu-id="068e2-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="068e2-282">UNIQUE</span></span>|<span data-ttu-id="068e2-283">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-283">Boolean</span></span>|  
|<span data-ttu-id="068e2-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="068e2-284">CLUSTERED</span></span>|<span data-ttu-id="068e2-285">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-285">Boolean</span></span>|  
|<span data-ttu-id="068e2-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-286">TYPE</span></span>|<span data-ttu-id="068e2-287">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-287">Int32</span></span>|  
|<span data-ttu-id="068e2-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="068e2-288">FILL_FACTOR</span></span>|<span data-ttu-id="068e2-289">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-289">Int32</span></span>|  
|<span data-ttu-id="068e2-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="068e2-290">INITIAL_SIZE</span></span>|<span data-ttu-id="068e2-291">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-291">Int32</span></span>|  
|<span data-ttu-id="068e2-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="068e2-292">NULLS</span></span>|<span data-ttu-id="068e2-293">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-293">Int32</span></span>|  
|<span data-ttu-id="068e2-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="068e2-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="068e2-295">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-295">Boolean</span></span>|  
|<span data-ttu-id="068e2-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="068e2-296">AUTO_UPDATE</span></span>|<span data-ttu-id="068e2-297">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-297">Boolean</span></span>|  
|<span data-ttu-id="068e2-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="068e2-298">NULL_COLLATION</span></span>|<span data-ttu-id="068e2-299">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-299">Int32</span></span>|  
|<span data-ttu-id="068e2-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-301">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-301">Int64</span></span>|  
|<span data-ttu-id="068e2-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-302">COLUMN_NAME</span></span>|<span data-ttu-id="068e2-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-303">String</span></span>|  
|<span data-ttu-id="068e2-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-304">COLUMN_GUID</span></span>|<span data-ttu-id="068e2-305">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-305">Guid</span></span>|  
|<span data-ttu-id="068e2-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-306">COLUMN_PROPID</span></span>|<span data-ttu-id="068e2-307">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-307">Int64</span></span>|  
|<span data-ttu-id="068e2-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="068e2-308">COLLATION</span></span>|<span data-ttu-id="068e2-309">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-309">Int16</span></span>|  
|<span data-ttu-id="068e2-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="068e2-310">CARDINALITY</span></span>|<span data-ttu-id="068e2-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="068e2-311">Decimal</span></span>|  
|<span data-ttu-id="068e2-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="068e2-312">PAGES</span></span>|<span data-ttu-id="068e2-313">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-313">Int32</span></span>|  
|<span data-ttu-id="068e2-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="068e2-314">FILTER_CONDITION</span></span>|<span data-ttu-id="068e2-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-315">String</span></span>|  
|<span data-ttu-id="068e2-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="068e2-316">INTEGRATED</span></span>|<span data-ttu-id="068e2-317">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="068e2-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="068e2-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="068e2-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="068e2-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="068e2-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="068e2-320">Tables</span></span>  
  
- <span data-ttu-id="068e2-321">Spalten</span><span class="sxs-lookup"><span data-stu-id="068e2-321">Columns</span></span>  
  
- <span data-ttu-id="068e2-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="068e2-322">Procedures</span></span>  
  
- <span data-ttu-id="068e2-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="068e2-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="068e2-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="068e2-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="068e2-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="068e2-325">Views</span></span>  
  
- <span data-ttu-id="068e2-326">Indizes</span><span class="sxs-lookup"><span data-stu-id="068e2-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="068e2-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="068e2-327">Tables</span></span>  
  
|<span data-ttu-id="068e2-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-328">ColumnName</span></span>|<span data-ttu-id="068e2-329">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-330">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-331">String</span></span>|  
|<span data-ttu-id="068e2-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-333">String</span></span>|  
|<span data-ttu-id="068e2-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-334">TABLE_NAME</span></span>|<span data-ttu-id="068e2-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-335">String</span></span>|  
|<span data-ttu-id="068e2-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-336">TABLE_TYPE</span></span>|<span data-ttu-id="068e2-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-337">String</span></span>|  
|<span data-ttu-id="068e2-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-338">TABLE_GUID</span></span>|<span data-ttu-id="068e2-339">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-339">Guid</span></span>|  
|<span data-ttu-id="068e2-340">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-340">DESCRIPTION</span></span>|<span data-ttu-id="068e2-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-341">String</span></span>|  
|<span data-ttu-id="068e2-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-342">TABLE_PROPID</span></span>|<span data-ttu-id="068e2-343">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-343">Int64</span></span>|  
|<span data-ttu-id="068e2-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-344">DATE_CREATED</span></span>|<span data-ttu-id="068e2-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-345">DateTime</span></span>|  
|<span data-ttu-id="068e2-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-346">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="068e2-348">Spalten</span><span class="sxs-lookup"><span data-stu-id="068e2-348">Columns</span></span>  
  
|<span data-ttu-id="068e2-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-349">ColumnName</span></span>|<span data-ttu-id="068e2-350">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-351">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-352">String</span></span>|  
|<span data-ttu-id="068e2-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-354">String</span></span>|  
|<span data-ttu-id="068e2-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-355">TABLE_NAME</span></span>|<span data-ttu-id="068e2-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-356">String</span></span>|  
|<span data-ttu-id="068e2-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-357">COLUMN_NAME</span></span>|<span data-ttu-id="068e2-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-358">String</span></span>|  
|<span data-ttu-id="068e2-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-359">COLUMN_GUID</span></span>|<span data-ttu-id="068e2-360">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-360">Guid</span></span>|  
|<span data-ttu-id="068e2-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-361">COLUMN_PROPID</span></span>|<span data-ttu-id="068e2-362">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-362">Int64</span></span>|  
|<span data-ttu-id="068e2-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-364">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-364">Int64</span></span>|  
|<span data-ttu-id="068e2-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="068e2-366">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-366">Boolean</span></span>|  
|<span data-ttu-id="068e2-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="068e2-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-368">String</span></span>|  
|<span data-ttu-id="068e2-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="068e2-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="068e2-370">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-370">Int64</span></span>|  
|<span data-ttu-id="068e2-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="068e2-371">IS_NULLABLE</span></span>|<span data-ttu-id="068e2-372">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-372">Boolean</span></span>|  
|<span data-ttu-id="068e2-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-373">DATA_TYPE</span></span>|<span data-ttu-id="068e2-374">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-374">Int32</span></span>|  
|<span data-ttu-id="068e2-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-375">TYPE_GUID</span></span>|<span data-ttu-id="068e2-376">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-376">Guid</span></span>|  
|<span data-ttu-id="068e2-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="068e2-378">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-378">Int64</span></span>|  
|<span data-ttu-id="068e2-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="068e2-380">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-380">Int64</span></span>|  
|<span data-ttu-id="068e2-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="068e2-382">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-382">Int32</span></span>|  
|<span data-ttu-id="068e2-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="068e2-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="068e2-384">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-384">Int16</span></span>|  
|<span data-ttu-id="068e2-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="068e2-386">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-386">Int64</span></span>|  
|<span data-ttu-id="068e2-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="068e2-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-388">String</span></span>|  
|<span data-ttu-id="068e2-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="068e2-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-390">String</span></span>|  
|<span data-ttu-id="068e2-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="068e2-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-392">String</span></span>|  
|<span data-ttu-id="068e2-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="068e2-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-394">String</span></span>|  
|<span data-ttu-id="068e2-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="068e2-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-396">String</span></span>|  
|<span data-ttu-id="068e2-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-397">COLLATION_NAME</span></span>|<span data-ttu-id="068e2-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-398">String</span></span>|  
|<span data-ttu-id="068e2-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="068e2-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-400">String</span></span>|  
|<span data-ttu-id="068e2-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="068e2-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-402">String</span></span>|  
|<span data-ttu-id="068e2-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-403">DOMAIN_NAME</span></span>|<span data-ttu-id="068e2-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-404">String</span></span>|  
|<span data-ttu-id="068e2-405">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-405">DESCRIPTION</span></span>|<span data-ttu-id="068e2-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="068e2-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="068e2-407">Procedures</span></span>  
  
|<span data-ttu-id="068e2-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-408">ColumnName</span></span>|<span data-ttu-id="068e2-409">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="068e2-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-411">String</span></span>|  
|<span data-ttu-id="068e2-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="068e2-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-413">String</span></span>|  
|<span data-ttu-id="068e2-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="068e2-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-415">String</span></span>|  
|<span data-ttu-id="068e2-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="068e2-417">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-417">Int16</span></span>|  
|<span data-ttu-id="068e2-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="068e2-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="068e2-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-419">String</span></span>|  
|<span data-ttu-id="068e2-420">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-420">DESCRIPTION</span></span>|<span data-ttu-id="068e2-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-421">String</span></span>|  
|<span data-ttu-id="068e2-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-422">DATE_CREATED</span></span>|<span data-ttu-id="068e2-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-423">DateTime</span></span>|  
|<span data-ttu-id="068e2-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-424">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="068e2-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="068e2-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="068e2-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-427">ColumnName</span></span>|<span data-ttu-id="068e2-428">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="068e2-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-430">String</span></span>|  
|<span data-ttu-id="068e2-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="068e2-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-432">String</span></span>|  
|<span data-ttu-id="068e2-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="068e2-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-434">String</span></span>|  
|<span data-ttu-id="068e2-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-435">COLUMN_NAME</span></span>|<span data-ttu-id="068e2-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-436">String</span></span>|  
|<span data-ttu-id="068e2-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-437">COLUMN_GUID</span></span>|<span data-ttu-id="068e2-438">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-438">Guid</span></span>|  
|<span data-ttu-id="068e2-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-439">COLUMN_PROPID</span></span>|<span data-ttu-id="068e2-440">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-440">Int64</span></span>|  
|<span data-ttu-id="068e2-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="068e2-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="068e2-442">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-442">Int64</span></span>|  
|<span data-ttu-id="068e2-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-444">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-444">Int64</span></span>|  
|<span data-ttu-id="068e2-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="068e2-445">IS_NULLABLE</span></span>|<span data-ttu-id="068e2-446">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-446">Boolean</span></span>|  
|<span data-ttu-id="068e2-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-447">DATA_TYPE</span></span>|<span data-ttu-id="068e2-448">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-448">Int32</span></span>|  
|<span data-ttu-id="068e2-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-449">TYPE_GUID</span></span>|<span data-ttu-id="068e2-450">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-450">Guid</span></span>|  
|<span data-ttu-id="068e2-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="068e2-452">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-452">Int64</span></span>|  
|<span data-ttu-id="068e2-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="068e2-454">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-454">Int64</span></span>|  
|<span data-ttu-id="068e2-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="068e2-456">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-456">Int32</span></span>|  
|<span data-ttu-id="068e2-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="068e2-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="068e2-458">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-458">Int16</span></span>|  
|<span data-ttu-id="068e2-459">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-459">DESCRIPTION</span></span>|<span data-ttu-id="068e2-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-460">String</span></span>|  
|<span data-ttu-id="068e2-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="068e2-461">OVERLOAD</span></span>|<span data-ttu-id="068e2-462">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="068e2-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="068e2-463">Views</span></span>  
  
|<span data-ttu-id="068e2-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-464">ColumnName</span></span>|<span data-ttu-id="068e2-465">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-466">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-467">String</span></span>|  
|<span data-ttu-id="068e2-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-469">String</span></span>|  
|<span data-ttu-id="068e2-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-470">TABLE_NAME</span></span>|<span data-ttu-id="068e2-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-471">String</span></span>|  
|<span data-ttu-id="068e2-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="068e2-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="068e2-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-473">String</span></span>|  
|<span data-ttu-id="068e2-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="068e2-474">CHECK_OPTION</span></span>|<span data-ttu-id="068e2-475">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-475">Boolean</span></span>|  
|<span data-ttu-id="068e2-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="068e2-476">IS_UPDATABLE</span></span>|<span data-ttu-id="068e2-477">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-477">Boolean</span></span>|  
|<span data-ttu-id="068e2-478">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-478">DESCRIPTION</span></span>|<span data-ttu-id="068e2-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-479">String</span></span>|  
|<span data-ttu-id="068e2-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-480">DATE_CREATED</span></span>|<span data-ttu-id="068e2-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-481">DateTime</span></span>|  
|<span data-ttu-id="068e2-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-482">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="068e2-484">Indizes</span><span class="sxs-lookup"><span data-stu-id="068e2-484">Indexes</span></span>  
  
|<span data-ttu-id="068e2-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-485">ColumnName</span></span>|<span data-ttu-id="068e2-486">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-487">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-488">String</span></span>|  
|<span data-ttu-id="068e2-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-490">String</span></span>|  
|<span data-ttu-id="068e2-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-491">TABLE_NAME</span></span>|<span data-ttu-id="068e2-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-492">String</span></span>|  
|<span data-ttu-id="068e2-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-493">INDEX_CATALOG</span></span>|<span data-ttu-id="068e2-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-494">String</span></span>|  
|<span data-ttu-id="068e2-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="068e2-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-496">String</span></span>|  
|<span data-ttu-id="068e2-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-497">INDEX_NAME</span></span>|<span data-ttu-id="068e2-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-498">String</span></span>|  
|<span data-ttu-id="068e2-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="068e2-499">PRIMARY_KEY</span></span>|<span data-ttu-id="068e2-500">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-500">Boolean</span></span>|  
|<span data-ttu-id="068e2-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="068e2-501">UNIQUE</span></span>|<span data-ttu-id="068e2-502">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-502">Boolean</span></span>|  
|<span data-ttu-id="068e2-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="068e2-503">CLUSTERED</span></span>|<span data-ttu-id="068e2-504">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-504">Boolean</span></span>|  
|<span data-ttu-id="068e2-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-505">TYPE</span></span>|<span data-ttu-id="068e2-506">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-506">Int32</span></span>|  
|<span data-ttu-id="068e2-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="068e2-507">FILL_FACTOR</span></span>|<span data-ttu-id="068e2-508">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-508">Int32</span></span>|  
|<span data-ttu-id="068e2-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="068e2-509">INITIAL_SIZE</span></span>|<span data-ttu-id="068e2-510">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-510">Int32</span></span>|  
|<span data-ttu-id="068e2-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="068e2-511">NULLS</span></span>|<span data-ttu-id="068e2-512">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-512">Int32</span></span>|  
|<span data-ttu-id="068e2-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="068e2-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="068e2-514">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-514">Boolean</span></span>|  
|<span data-ttu-id="068e2-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="068e2-515">AUTO_UPDATE</span></span>|<span data-ttu-id="068e2-516">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-516">Boolean</span></span>|  
|<span data-ttu-id="068e2-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="068e2-517">NULL_COLLATION</span></span>|<span data-ttu-id="068e2-518">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-518">Int32</span></span>|  
|<span data-ttu-id="068e2-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-520">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-520">Int64</span></span>|  
|<span data-ttu-id="068e2-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-521">COLUMN_NAME</span></span>|<span data-ttu-id="068e2-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-522">String</span></span>|  
|<span data-ttu-id="068e2-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-523">COLUMN_GUID</span></span>|<span data-ttu-id="068e2-524">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-524">Guid</span></span>|  
|<span data-ttu-id="068e2-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-525">COLUMN_PROPID</span></span>|<span data-ttu-id="068e2-526">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-526">Int64</span></span>|  
|<span data-ttu-id="068e2-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="068e2-527">COLLATION</span></span>|<span data-ttu-id="068e2-528">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-528">Int16</span></span>|  
|<span data-ttu-id="068e2-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="068e2-529">CARDINALITY</span></span>|<span data-ttu-id="068e2-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="068e2-530">Decimal</span></span>|  
|<span data-ttu-id="068e2-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="068e2-531">PAGES</span></span>|<span data-ttu-id="068e2-532">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-532">Int32</span></span>|  
|<span data-ttu-id="068e2-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="068e2-533">FILTER_CONDITION</span></span>|<span data-ttu-id="068e2-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-534">String</span></span>|  
|<span data-ttu-id="068e2-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="068e2-535">INTEGRATED</span></span>|<span data-ttu-id="068e2-536">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="068e2-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="068e2-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="068e2-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="068e2-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="068e2-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="068e2-539">Tables</span></span>  
  
- <span data-ttu-id="068e2-540">Spalten</span><span class="sxs-lookup"><span data-stu-id="068e2-540">Columns</span></span>  
  
- <span data-ttu-id="068e2-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="068e2-541">Procedures</span></span>  
  
- <span data-ttu-id="068e2-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="068e2-542">Views</span></span>  
  
- <span data-ttu-id="068e2-543">Indizes</span><span class="sxs-lookup"><span data-stu-id="068e2-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="068e2-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="068e2-544">Tables</span></span>  
  
|<span data-ttu-id="068e2-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-545">ColumnName</span></span>|<span data-ttu-id="068e2-546">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-547">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-548">String</span></span>|  
|<span data-ttu-id="068e2-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-550">String</span></span>|  
|<span data-ttu-id="068e2-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-551">TABLE_NAME</span></span>|<span data-ttu-id="068e2-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-552">String</span></span>|  
|<span data-ttu-id="068e2-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-553">TABLE_TYPE</span></span>|<span data-ttu-id="068e2-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-554">String</span></span>|  
|<span data-ttu-id="068e2-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-555">TABLE_GUID</span></span>|<span data-ttu-id="068e2-556">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-556">Guid</span></span>|  
|<span data-ttu-id="068e2-557">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-557">DESCRIPTION</span></span>|<span data-ttu-id="068e2-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-558">String</span></span>|  
|<span data-ttu-id="068e2-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-559">TABLE_PROPID</span></span>|<span data-ttu-id="068e2-560">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-560">Int64</span></span>|  
|<span data-ttu-id="068e2-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-561">DATE_CREATED</span></span>|<span data-ttu-id="068e2-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-562">DateTime</span></span>|  
|<span data-ttu-id="068e2-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-563">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="068e2-565">Spalten</span><span class="sxs-lookup"><span data-stu-id="068e2-565">Columns</span></span>  
  
|<span data-ttu-id="068e2-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-566">ColumnName</span></span>|<span data-ttu-id="068e2-567">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-568">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-569">String</span></span>|  
|<span data-ttu-id="068e2-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-571">String</span></span>|  
|<span data-ttu-id="068e2-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-572">TABLE_NAME</span></span>|<span data-ttu-id="068e2-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-573">String</span></span>|  
|<span data-ttu-id="068e2-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-574">COLUMN_NAME</span></span>|<span data-ttu-id="068e2-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-575">String</span></span>|  
|<span data-ttu-id="068e2-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-576">COLUMN_GUID</span></span>|<span data-ttu-id="068e2-577">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-577">Guid</span></span>|  
|<span data-ttu-id="068e2-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-578">COLUMN_PROPID</span></span>|<span data-ttu-id="068e2-579">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-579">Int64</span></span>|  
|<span data-ttu-id="068e2-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-581">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-581">Int64</span></span>|  
|<span data-ttu-id="068e2-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="068e2-583">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-583">Boolean</span></span>|  
|<span data-ttu-id="068e2-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="068e2-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="068e2-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-585">String</span></span>|  
|<span data-ttu-id="068e2-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="068e2-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="068e2-587">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-587">Int64</span></span>|  
|<span data-ttu-id="068e2-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="068e2-588">IS_NULLABLE</span></span>|<span data-ttu-id="068e2-589">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-589">Boolean</span></span>|  
|<span data-ttu-id="068e2-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-590">DATA_TYPE</span></span>|<span data-ttu-id="068e2-591">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-591">Int32</span></span>|  
|<span data-ttu-id="068e2-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-592">TYPE_GUID</span></span>|<span data-ttu-id="068e2-593">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-593">Guid</span></span>|  
|<span data-ttu-id="068e2-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="068e2-595">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-595">Int64</span></span>|  
|<span data-ttu-id="068e2-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="068e2-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="068e2-597">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-597">Int64</span></span>|  
|<span data-ttu-id="068e2-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="068e2-599">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-599">Int32</span></span>|  
|<span data-ttu-id="068e2-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="068e2-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="068e2-601">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-601">Int16</span></span>|  
|<span data-ttu-id="068e2-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="068e2-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="068e2-603">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-603">Int64</span></span>|  
|<span data-ttu-id="068e2-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="068e2-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-605">String</span></span>|  
|<span data-ttu-id="068e2-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="068e2-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-607">String</span></span>|  
|<span data-ttu-id="068e2-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="068e2-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-609">String</span></span>|  
|<span data-ttu-id="068e2-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="068e2-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-611">String</span></span>|  
|<span data-ttu-id="068e2-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="068e2-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-613">String</span></span>|  
|<span data-ttu-id="068e2-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-614">COLLATION_NAME</span></span>|<span data-ttu-id="068e2-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-615">String</span></span>|  
|<span data-ttu-id="068e2-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="068e2-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-617">String</span></span>|  
|<span data-ttu-id="068e2-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="068e2-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-619">String</span></span>|  
|<span data-ttu-id="068e2-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-620">DOMAIN_NAME</span></span>|<span data-ttu-id="068e2-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-621">String</span></span>|  
|<span data-ttu-id="068e2-622">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-622">DESCRIPTION</span></span>|<span data-ttu-id="068e2-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="068e2-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="068e2-624">Procedures</span></span>  
  
|<span data-ttu-id="068e2-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-625">ColumnName</span></span>|<span data-ttu-id="068e2-626">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="068e2-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-628">String</span></span>|  
|<span data-ttu-id="068e2-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="068e2-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-630">String</span></span>|  
|<span data-ttu-id="068e2-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="068e2-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-632">String</span></span>|  
|<span data-ttu-id="068e2-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="068e2-634">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-634">Int16</span></span>|  
|<span data-ttu-id="068e2-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="068e2-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="068e2-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-636">String</span></span>|  
|<span data-ttu-id="068e2-637">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-637">DESCRIPTION</span></span>|<span data-ttu-id="068e2-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-638">String</span></span>|  
|<span data-ttu-id="068e2-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-639">DATE_CREATED</span></span>|<span data-ttu-id="068e2-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-640">DateTime</span></span>|  
|<span data-ttu-id="068e2-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-641">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="068e2-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="068e2-643">Views</span></span>  
  
|<span data-ttu-id="068e2-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-644">ColumnName</span></span>|<span data-ttu-id="068e2-645">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-646">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-647">String</span></span>|  
|<span data-ttu-id="068e2-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-649">String</span></span>|  
|<span data-ttu-id="068e2-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-650">TABLE_NAME</span></span>|<span data-ttu-id="068e2-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-651">String</span></span>|  
|<span data-ttu-id="068e2-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="068e2-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="068e2-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-653">String</span></span>|  
|<span data-ttu-id="068e2-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="068e2-654">CHECK_OPTION</span></span>|<span data-ttu-id="068e2-655">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-655">Boolean</span></span>|  
|<span data-ttu-id="068e2-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="068e2-656">IS_UPDATABLE</span></span>|<span data-ttu-id="068e2-657">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-657">Boolean</span></span>|  
|<span data-ttu-id="068e2-658">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="068e2-658">DESCRIPTION</span></span>|<span data-ttu-id="068e2-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-659">String</span></span>|  
|<span data-ttu-id="068e2-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="068e2-660">DATE_CREATED</span></span>|<span data-ttu-id="068e2-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-661">DateTime</span></span>|  
|<span data-ttu-id="068e2-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="068e2-662">DATE_MODIFIED</span></span>|<span data-ttu-id="068e2-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="068e2-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="068e2-664">Indizes</span><span class="sxs-lookup"><span data-stu-id="068e2-664">Indexes</span></span>  
  
|<span data-ttu-id="068e2-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="068e2-665">ColumnName</span></span>|<span data-ttu-id="068e2-666">DataType</span><span class="sxs-lookup"><span data-stu-id="068e2-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="068e2-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-667">TABLE_CATALOG</span></span>|<span data-ttu-id="068e2-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-668">String</span></span>|  
|<span data-ttu-id="068e2-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="068e2-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-670">String</span></span>|  
|<span data-ttu-id="068e2-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-671">TABLE_NAME</span></span>|<span data-ttu-id="068e2-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-672">String</span></span>|  
|<span data-ttu-id="068e2-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="068e2-673">INDEX_CATALOG</span></span>|<span data-ttu-id="068e2-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-674">String</span></span>|  
|<span data-ttu-id="068e2-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="068e2-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="068e2-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-676">String</span></span>|  
|<span data-ttu-id="068e2-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-677">INDEX_NAME</span></span>|<span data-ttu-id="068e2-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-678">String</span></span>|  
|<span data-ttu-id="068e2-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="068e2-679">PRIMARY_KEY</span></span>|<span data-ttu-id="068e2-680">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-680">Boolean</span></span>|  
|<span data-ttu-id="068e2-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="068e2-681">UNIQUE</span></span>|<span data-ttu-id="068e2-682">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-682">Boolean</span></span>|  
|<span data-ttu-id="068e2-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="068e2-683">CLUSTERED</span></span>|<span data-ttu-id="068e2-684">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-684">Boolean</span></span>|  
|<span data-ttu-id="068e2-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="068e2-685">TYPE</span></span>|<span data-ttu-id="068e2-686">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-686">Int32</span></span>|  
|<span data-ttu-id="068e2-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="068e2-687">FILL_FACTOR</span></span>|<span data-ttu-id="068e2-688">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-688">Int32</span></span>|  
|<span data-ttu-id="068e2-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="068e2-689">INITIAL_SIZE</span></span>|<span data-ttu-id="068e2-690">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-690">Int32</span></span>|  
|<span data-ttu-id="068e2-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="068e2-691">NULLS</span></span>|<span data-ttu-id="068e2-692">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-692">Int32</span></span>|  
|<span data-ttu-id="068e2-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="068e2-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="068e2-694">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-694">Boolean</span></span>|  
|<span data-ttu-id="068e2-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="068e2-695">AUTO_UPDATE</span></span>|<span data-ttu-id="068e2-696">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-696">Boolean</span></span>|  
|<span data-ttu-id="068e2-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="068e2-697">NULL_COLLATION</span></span>|<span data-ttu-id="068e2-698">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-698">Int32</span></span>|  
|<span data-ttu-id="068e2-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="068e2-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="068e2-700">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-700">Int64</span></span>|  
|<span data-ttu-id="068e2-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="068e2-701">COLUMN_NAME</span></span>|<span data-ttu-id="068e2-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-702">String</span></span>|  
|<span data-ttu-id="068e2-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-703">COLUMN_GUID</span></span>|<span data-ttu-id="068e2-704">GUID</span><span class="sxs-lookup"><span data-stu-id="068e2-704">Guid</span></span>|  
|<span data-ttu-id="068e2-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="068e2-705">COLUMN_PROPID</span></span>|<span data-ttu-id="068e2-706">Int64</span><span class="sxs-lookup"><span data-stu-id="068e2-706">Int64</span></span>|  
|<span data-ttu-id="068e2-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="068e2-707">COLLATION</span></span>|<span data-ttu-id="068e2-708">Int16</span><span class="sxs-lookup"><span data-stu-id="068e2-708">Int16</span></span>|  
|<span data-ttu-id="068e2-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="068e2-709">CARDINALITY</span></span>|<span data-ttu-id="068e2-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="068e2-710">Decimal</span></span>|  
|<span data-ttu-id="068e2-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="068e2-711">PAGES</span></span>|<span data-ttu-id="068e2-712">Int32</span><span class="sxs-lookup"><span data-stu-id="068e2-712">Int32</span></span>|  
|<span data-ttu-id="068e2-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="068e2-713">FILTER_CONDITION</span></span>|<span data-ttu-id="068e2-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="068e2-714">String</span></span>|  
|<span data-ttu-id="068e2-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="068e2-715">INTEGRATED</span></span>|<span data-ttu-id="068e2-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="068e2-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="068e2-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="068e2-717">See also</span></span>

- [<span data-ttu-id="068e2-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="068e2-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

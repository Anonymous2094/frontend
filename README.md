<!-- <?php
$desc = $this->session->userdata('desc');
$desc = json_decode($desc);
$desc = objectToArray($desc);
$vouchers = $desc['vouchers'];
?> -->

<!-- Content Header (Page header) -->
<!-- main content -->
<div id="main_wrapper">

    <div class="page_bar">
        <div class="row">
            <div class="col-md-12">
                <h1 class="page_title">Add New Courier Wise City</h1>
            </div>
        </div>
    </div>
    
    <div class="page_content">
        <div class="container-fluid">

            <div class="row">
                <div class="col-md-12">

                    <div class="row">
                        <div class="col-lg-12">
                            <div class="panel panel-default">
                                <div class="panel-body">

                                    <form action="">

                                        <div class="row">
                                            <div class="col-lg-2">
                                                <div class="input-group">
                                                    <span class="input-group-addon id-addon VoucherNoLableShort">Vr#</span>
                                                    <input type="number" class="form-control input-sm VoucherNo" id="txtVrnoa" >
                                                    <input type="hidden" id="txtMaxVrnoaHidden">
                                                    <input type="hidden" id="txtVrnoaHidden">
                                                    <input type="hidden" id="voucher_type_hidden">
                                                    <input type="hidden" id="voucher_bulk_hidden">



                                                </div>
                                            </div>
                                            <div class="col-lg-2">
                                                <div class="input-group">
                                                    <span class="input-group-addon txt-addon">Date</span>
                                                    <input class="form-control input-sm" type="date" id="cur_date" value="<?php echo date('Y-m-d'); ?>" >
                                                    <input class="form-control input-sm hidden" type="date" id="chk_date" value="<?php echo date('Y-m-d'); ?>" >
                                                    
                                                </div>
                                            </div>
                                            <div class="col-lg-2">
                                                <div class="input-group">
                                                    <div class="input-group-addon id-addon">Is active?</div>


                                                    <input type="checkbox" checked="" class="bs_switch active_switch" id="active">
                                                </div>
                                            </div>


                                        </div>
                                        <div class="row">
                                            <div class="col-lg-6">
                                                <div class="input-group">
                                                    <span class="input-group-addon txt-addon">Account</span>
                                                    <input type="hidden" name="uid" id="uid" value="<?php echo $this->session->userdata('uid'); ?>">

                                                    <input type="text" class="form-control" id="txtPartyId"  >
                                                    <input id="hfPartyId" type="hidden" value="<?php echo $this->session->userdata('user_pid'); ?>" />
                                                    <input id="hfPartyCity" type="hidden" value="" />
                                                    <input id="hfPartyAddress" type="hidden" value="" />
                                                    <input id="hfPartyCityArea" type="hidden" value="" />
                                                    <input id="hfPartyMobile" type="hidden" value="" />
                                                    <input id="hfPartyUname" type="hidden" value="" />
                                                    <input id="hfPartyLimit" type="hidden" value="" />
                                                    <input id="hfPartyName" type="hidden" value="" />
                                                    <input id="txtHiddenEditQty" type="hidden" value="" />
                                                    <input id="txtHiddenEditRow" type="hidden" value="" />
                                                </div>

                                            </div>

                                            <div class="col-lg-2">
                                                <div class="input-group">
                                                    <div class="input-group-addon id-addon">Contract Type</div>


                                                    <select class="form-control" id="contracttype_dropdown">
                                                            <option value="weight" selected="" >Weight Wise</option>
                                                            <option value="percentage"  >Percentage Wise</option>
                                                      
                                                      </select>

                                                </div>
                                            </div>

                                            <div class="col-lg-2">
                                                <div class="input-group">
                                                    <div class="input-group-addon id-addon">Min Charges</div>

                                                    <input type="text" class="form-control" id="txtMinCharges">

                                                    
                                                </div>
                                            </div>

                                            <div class="col-lg-2">
                                                <div class="input-group">
                                                    <div class="input-group-addon id-addon">Percentage</div>

                                                    <input type="text" class="form-control" id="txtPercentage">

                                                    
                                                </div>
                                            </div>

                                        </div>


                                        <div class="row">

                                            <div class="col-lg-6">
                                                <div class="input-group">
                                                    <span class="input-group-addon txt-addon">Remarks</span>
                                                    <input type="text" class="form-control" id="txtRemarks">
                                                    
                                                </div>
                                            </div>
                                        </div>

                                        <div class="row">
                                            <div class="col-lg-12">
                                                <div class="container-wrap">
                                                  <div class="row">
                                                    <div class="col-lg-2">                                                
                                                        <label>City</label>

                                                        <select class="form-control select2" id="city_dropdown">
                                                            <option value="" selected="" disabled="">Choose City...</option>
                                                            <?php foreach ($cities as $c): ?>

                                                              <option value="<?php echo $c['city_id']; ?>"><?php echo $c['name']; ?></option>
                                                          <?php endforeach ?>
                                                      </select>

                                                  </div>

                                                  <div class="col-lg-1">
                                                      <label for="">Weight From</label>                                                    
                                                      <input type="text" class="form-control num text-right" id="txtWeightFrom">                                                    
                                                  </div>

                                                  <div class="col-lg-1">
                                                    <label for="">Weight To</label>                                                    
                                                    <input type="text" class="form-control num text-right" id="txtWeightTo">                                                    
                                                </div>


                                                <div class="col-lg-2">
                                                    <label for="">Narration</label>                                                    
                                                    <input type="text" class="form-control" id="txtNarration">                                                    
                                                </div>
                                                <div class="col-lg-1">
                                                    <label>Add</label>
                                                    <a href="" class="btn btn-primary" id="btnAdd">+</a>
                                                </div>
                                            </div>
                                        </div>
                                    </div>



                                </div>



                                <div class="row">
                                    <div class="col-lg-6">
                                        <table class="table table-striped" id="purchase_table">
                                            <thead>
                                                <tr>
                                                    <th>Sr#</th>
                                                    <th class="text-left">City</th>
                                                    <th class="text-right">Weight From</th>
                                                    <th class="text-right">Weight To</th>
                                                    <th class="text-right hide">With In City</th>
                                                    <th class="text-right hide">Same Zone</th>
                                                    <th class="text-right hide">Diffrent Zone</th>
                                                    <th class="text-left">Narration</th>
                                                    <th>Action</th>
                                                </tr>
                                            </thead>
                                            <tbody class="saleRows">

                                            </tbody>
                                            <tfoot class="tfoot_tbl ">
                                                <tr>
                                                    <td class="text-right"></td>
                                                    <td class="text-right "></td>
                                                    <td class="text-right "></td>
                                                    <td class="hide"></td>
                                                    <td class="hide"></td>
                                                    <td class="hide"></td>
                                                    <td ></td>
                                                    <td ></td>
                                                    <td ></td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                </div>

                                <div class="row">
                                    <div class="col-lg-6    ">
                                        <label>Note</label>
                                        <textarea class="form-control"  rows="10"  id="txtNote">

                                        </textarea>

                                    </div>

                                </div>


                            </div>





                        </form> <!-- end of form -->

                    </div>  <!-- end of panel-body -->
                </div>  <!-- end of panel -->
            </div>  <!-- end of col -->
        </div>  <!-- end of row -->



    </div>  <!-- end of level 1-->
    <div class="row">
        <div class="col-lg-12">
            <div class="panel panel-default">
                <div class="panel-body">

                    <div class="row">
                        <div class="col-lg-8">
                            <div class="row">
                                <div class="col-lg-12">
                                    <a class="btn btn-default btnReset"><i class="fa fa-refresh"></i> Reset F5</a>
                                    <a class="btn btn-default btnSave" data-saveaccountbtn='<?php echo $vouchers['account']['insert']; ?>' data-saveitembtn='<?php echo $vouchers['item']['insert']; ?>' data-insertbtn='<?php echo $vouchers['couriercity']['insert']; ?>' data-updatebtn='<?php echo $vouchers['couriercity']['update']; ?>' data-deletebtn='<?php echo $vouchers['couriercity']['delete']; ?>' data-printbtn='<?php echo $vouchers['couriercity']['print']; ?>' ><i class="fa fa-save"></i> Save F10</a>
                                    <a class="btn btn-default btnDelete"><i class="fa fa-trash-o"></i> Delete F12</a>

                                    <div class="btn-group">
                                        <button type="button" class="btn btn-default btnPrint " ><i class="fa fa-save"></i>Print F9</button>


                                    </div>
                                </div>
                            </div>
                        </div>  


                    </div>  <!-- end of row -->
                    <br>
                    <div class="row">
                        <div class="col-lg-4">
                            <div class="form-group">                                                                
                                <div class="input-group">
                                  <span class="switch-addon">Print Header?</span>
                                  <input type="checkbox" checked="" class="bs_switch" id="switchPrintHeader">
                              </div>
                          </div>
                      </div>
                      <!-- <div class="col-lg-1"></div> -->
                      <div class="col-lg-3">
                        <div class="input-group">
                            <span class="input-group-addon txt-addon">User: </span>
                            <input type="text" class=" form-control"  id="txtUserName" readonly="true" >

                        </div>
                    </div>
                    <div class="col-lg-3">
                        <div class="input-group">
                            <span class="input-group-addon txt-addon">Posting: </span>
                            <input type="text" class=" form-control"  readonly="true" id="txtPostingDate" >

                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</div>
</div>
</div>
</div>

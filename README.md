""<div class="panel panel-default" style="margin-bottom: 20px;">
  <div class="panel-heading bg-primary text-white">
    🎯 Choisir le destinataire du message
  </div>
  <div class="panel-body">
    <!-- Sélecteur principal -->
    <div class="form-group">
      <label for="recipientType">Type de destinataire</label>
      <select class="form-control"
              id="recipientType"
              ng-model="formData.recipientType"
              ng-options="option.value as option.label for option in recipientOptions"
              ng-change="onRecipientTypeChange()">
      </select>
    </div>

    <!-- ID Client -->
    <div class="form-group" ng-if="formData.recipientType === 'customerById'">
      <label for="customerId">ID du client</label>
      <input type="number"
             class="form-control"
             id="customerId"
             placeholder="Ex : 1234"
             ng-model="formData.customerId">
    </div>

    <!-- Sélection admins -->
    <div class="form-group" ng-if="formData.recipientType === 'specificAdmins'">
      <label for="adminsList">Sélectionner les admins</label>
      <ui-select multiple
                 ng-model="formData.selectedAdmins"
                 theme="bootstrap"
                 close-on-select="false"
                 style="width: 100%;">
        <ui-select-match placeholder="Sélectionnez un ou plusieurs admins...">
          {{$item.name}}
        </ui-select-match>
        <ui-select-choices repeat="admin in admins | filter: $select.search">
          {{admin.name}} (ID: {{admin.id}})
        </ui-select-choices>
      </ui-select>
    </div>
  </div>
</div>
""

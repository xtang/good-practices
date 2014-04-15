- Update item in `ng-repeat`:

  ```html
  <!-- background -->
  <div ng-repeat="friend in friends" ng-click="change()">
    <p>{{friend.name}}</p>
    <p>{{friend.id}}</p>
  </div>
  ```

  ```javascript
  // good
  $scope.change = function() {
    angular.extend($scope.friend, {name: randName(), id: randId()})
  }

  // bad, even wrong, it will not change the value in `friends`
  $scope.change = function() {
    $scope.friend = {name: randName(), id: randId()}
  }
  ```

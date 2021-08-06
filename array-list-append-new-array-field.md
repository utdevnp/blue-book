 <pre>
 $orderList = $this->__pageModel->getOrderByCustomerId($formData['customer_id']);
                $newArray = [];
                foreach ($orderList as $order => $value) {

                    $newArray[$order] = $value;

                    $newArray[$order]['line_items'] = $this->__orderLineItemModel->getByOrderId($value['id']);

                }
                return $this->respond(array(
                    'status' => 'success',
                    'message' => 'Order list listed successfully',
                    'data' => $newArray
                ));
      </pre>

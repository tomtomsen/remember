
	<?php
	// PHP 5.3.3ish

    class BaseClass
    {
        static function instance()
        {
            return new static(); // returns "BaseClass"
            return new self();   // returns "AnotherClass"
        }

        public function getName()
        {
            return "BaseClass";
        }
    }

    class AnotherClass extends MyClass
    {
        public function getName()
        {
            return "AnotherClass";
        }
    }

    var_dump(AnotherClass::instance()->getName());



	<?php
	// PHP 5.3.3ish

	class BaseClass
	{
		public function getName()
		{
			return "BaseClass";
		}
	}

    class MyClass
    {
        static function instance()
        {
            return new static(); // liefert "Anoterclass"
            return new self();   // liefert "MyClass"

        	return new parent(); // funktioniert nicht !!!
        }

        public function getName()
        {
            return "MyClass";
        }
    }

    class AnotherClass extends MyClass
    {
        public function getName()
        {
            return "AnotherClass";
        }
    }

    // AnotherClass::instance
    var_dump(AnotherClass::instance()->getName());
